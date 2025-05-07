* *synced with daily-notes*
```dataviewjs
// --- Configuration ---
const FOLDER_PATH = '"09 Daily Notes"'; // <-- Make sure this path is EXACTLY correct
const WEIGHT_PROPERTY = 'Weight';     // <-- The property name in your daily notes
const CHART_TYPE = 'bar';             // <-- 'bar' or 'line' are common choices
const CHART_LABEL = 'Weight, Goal=62';         // <-- Label for the dataset
const BAR_BACKGROUND_COLOR = 'rgba(54, 162, 235, 0.2)'; // Example: Blue semi-transparent
const BAR_BORDER_COLOR = 'rgba(54, 162, 235, 1)';       // Example: Solid Blue
const BEGIN_AT_ZERO = false;           // <-- Set to 'true' if you want Y-axis to start at 0, 'false' is often better for weight

// --- Define Date Formats ---
const filenameDateFormat = "DD-MM-YYYY, dddd"; // <-- Your current filename format
const chartDateFormat = "YYYY-MM-DD";        // <-- Format needed for chart labels

// --- Dataview Query ---
// 1. Get pages from the specified folder
const pages = dv.pages(FOLDER_PATH)
    // 2. Filter for pages that have the Weight property defined
    //    (We can't reliably use p.file.day anymore for filtering)
    .where(p => p[WEIGHT_PROPERTY] !== undefined && p[WEIGHT_PROPERTY] !== null)
    // 3. Sort pages chronologically BY PARSING THE FILENAME
    .sort(p => moment(p.file.name, filenameDateFormat), 'asc');

// --- Data Extraction (Manual Parsing) ---
const labels = [];
const weights = [];

pages.forEach(p => {
    try {
        // Attempt to parse the date from the filename
        const dateMoment = moment(p.file.name, filenameDateFormat);

        // Check if the date was parsed successfully AND weight exists
        if (dateMoment.isValid() && p[WEIGHT_PROPERTY] !== undefined && p[WEIGHT_PROPERTY] !== null) {
            // Add the formatted date to labels
            labels.push(dateMoment.format(chartDateFormat));
            // Add the corresponding weight
            weights.push(p[WEIGHT_PROPERTY]);
        } else {
            // Optional: Log pages that couldn't be parsed or are missing weight
            console.warn(`Skipping page for chart (invalid date or missing weight): ${p.file.name}`);
        }
    } catch (e) {
        // Catch any unexpected errors during processing
        console.error(`Error processing page ${p.file.name} for chart:`, e);
    }
});


// --- Chart Definition (using Chart.js structure) ---
// This part remains unchanged as it uses the extracted 'labels' and 'weights'
const chartData = {
    type: CHART_TYPE,
    data: {
        labels: labels, // Use the extracted dates
        datasets: [{
            label: CHART_LABEL,             // Use the configured label
            data: weights,                  // Use the extracted weight data
            backgroundColor: [BAR_BACKGROUND_COLOR], // Apply background color
            borderColor: [BAR_BORDER_COLOR],         // Apply border color
            borderWidth: 1,
            // For line charts, you might want:
            // tension: 0.1, // Slightly curve the line
            // fill: true, // Fill area under the line
        }]
    },
    options: {
        animation: {
            duration: 0 // Disable animations
        },
        scales: {
            y: {
                beginAtZero: BEGIN_AT_ZERO // Control if Y-axis must start at 0
            }
        }
        // Add other Chart.js options here if needed
    }
};

// --- Render the Chart ---
// This part remains unchanged
window.renderChart(chartData, this.container);
```

```dataviewjs
// --- Calculate Study Streak ---
let currentStreak = 0;
try {
    const studiedPages = dv.pages('"09 Daily Notes"')
        .where(p => p.Studied)
        .sort(p => p.file.name, 'desc');

    const studiedDates = new Set(studiedPages.map(p => p.file.name));
    let checkDate = moment();

    if (!studiedDates.has(checkDate.format("DD-MM-YYYY, dddd"))) {
         checkDate.subtract(1, 'day');
         if (!studiedDates.has(checkDate.format("DD-MM-YYYY, dddd"))) {
             checkDate = null;
         }
    }

    if (checkDate) {
        while (studiedDates.has(checkDate.format("DD-MM-YYYY, dddd"))) {
            currentStreak++;
            checkDate.subtract(1, 'day');
        }
    }

} catch (e) {
    console.error("Error calculating study streak:", e);
    currentStreak = "Error";
}


// --- Display Title with Streak ---
dv.span(`**Study🪴 🔥${currentStreak}**`);


// --- Calendar Code ---
const calendarData = {
    intensityScaleEnd: 5,
    colors: {
        red: ["#11ff00", "#11ff00", "#11ff00", "#11ff00", "#11ff00"]
    },
    entries: []
}

const filenameDateFormat = "DD-MM-YYYY, dddd";
const heatmapDateFormat = "YYYY-MM-DD";

for(let page of dv.pages('"09 Daily Notes"').where(p => p.Studied)) {
    try {
        const dateMoment = moment(page.file.name, filenameDateFormat);

        if (dateMoment.isValid()) {
            const formattedDate = dateMoment.format(heatmapDateFormat);

            calendarData.entries.push({
                date: formattedDate,
                intensity: page.Studied,
            });
        } else {
             console.warn(`Could not parse date from filename for heatmap: ${page.file.name}`);
        }
    } catch (e) {
        console.error(`Error processing page ${page.file.name} for heatmap:`, e);
    }
}

renderHeatmapCalendar(this.container, calendarData)
```



```dataviewjs
// --- Calculate Workout Streak ---
let currentStreak = 0;
try {
    // Get pages with the 'Workout' field, sort by date descending
    const workoutPages = dv.pages('"09 Daily Notes"')
        .where(p => p.Workout) // Check if 'Workout' exists and is truthy
        .sort(p => p.file.name, 'desc'); // Sort by filename (date) descending

    // Create a Set of workout dates (DD-MM-YYYY, dddd format) for fast lookup
    const workoutDates = new Set(workoutPages.map(p => p.file.name));

    // Calculate streak starting from today/yesterday
    let checkDate = moment();

    // Check if today or yesterday has a workout record
    if (!workoutDates.has(checkDate.format("DD-MM-YYYY, dddd"))) {
        // Didn't workout today, check yesterday
        checkDate.subtract(1, 'day');
        if (!workoutDates.has(checkDate.format("DD-MM-YYYY, dddd"))) {
            // Didn't workout yesterday either, streak is 0
            checkDate = null; // Signal streak is 0
        }
    }
    // else: Worked out today, checkDate remains today.

    // If we have a valid starting point (today or yesterday worked out)
    if (checkDate) {
        while (workoutDates.has(checkDate.format("DD-MM-YYYY, dddd"))) {
            currentStreak++;
            checkDate.subtract(1, 'day'); // Move to check the previous day
        }
    }
    // If checkDate was null, currentStreak remains 0

} catch (e) {
    console.error("Error calculating workout streak:", e);
    currentStreak = "Error"; // Indicate error state
}


// --- Display Title with Streak ---
dv.span(`**Workout💪 🔥${currentStreak}**`);


// --- Calendar Code ---
const calendarData = {
    intensityScaleEnd: 5, // Assuming max intensity is 5 based on 'Workout' field values
    colors: {
        // Using 'red' key as in original, even if colors are blue. Change key if needed by library.
        red: ["#00ecff", "#00ecff", "#00ecff", "#00ecff", "#00ecff"]
    },
    entries: []
}

// Define the format your filenames are *currently* in
const filenameDateFormat = "DD-MM-YYYY, dddd";
// Define the format the heatmap library likely expects
const heatmapDateFormat = "YYYY-MM-DD";

for(let page of dv.pages('"09 Daily Notes"').where(p => p.Workout)) {
    try {
        // Parse the date from the filename using its specific format
        const dateMoment = moment(page.file.name, filenameDateFormat);

        // Check if the date was parsed successfully
        if (dateMoment.isValid()) {
            // Format the date into the standard YYYY-MM-DD format for the heatmap
            const formattedDate = dateMoment.format(heatmapDateFormat);

            calendarData.entries.push({
                date: formattedDate, // Use the CORRECTLY FORMATTED date here
                intensity: page.Workout, // Use the 'Workout' value for intensity
                // No 'content' property to avoid layout issues
            });
        } else {
             // Optional: Log a warning if a filename couldn't be parsed
             console.warn(`Could not parse date from filename for heatmap: ${page.file.name}`);
        }
    } catch (e) {
        console.error(`Error processing page ${page.file.name} for heatmap:`, e);
    }
}

// Render the heatmap
renderHeatmapCalendar(this.container, calendarData)
```


```dataviewjs
// --- Calculate 5x_Salah Streak ---
// Streak calculation remains the same as the previous corrected version
let currentStreak = 0;
try {
    const salahPages = dv.pages('"09 Daily Notes"')
        .where(p => p["5x_Salah"])
        .sort(p => p.file.name, 'desc');
    const filenameDateFormatStreak = "DD-MM-YYYY, dddd";
    const salahDates = new Set(salahPages.map(p => p.file.name));
    let checkDate = moment();
    if (!salahDates.has(checkDate.format(filenameDateFormatStreak))) {
         checkDate.subtract(1, 'day');
         if (!salahDates.has(checkDate.format(filenameDateFormatStreak))) {
             checkDate = null;
         }
    }
    if (checkDate) {
        while (salahDates.has(checkDate.format(filenameDateFormatStreak))) {
            currentStreak++;
            checkDate.subtract(1, 'day');
        }
    }
} catch (e) {
    console.error("Error calculating 5x_Salah streak:", e);
    currentStreak = "Error";
}

// --- Display Title with Streak ---
dv.span(`**5x_Salah🕋 🔥${currentStreak}**`);


// --- Calendar Code (Adjusted for Color Rendering) ---
const calendarData = {
    intensityScaleEnd: 5,
    colors: {
        red: ["#b600ff", "#b600ff", "#b600ff", "#b600ff", "#b600ff"]
    },
    entries: []
}

const filenameDateFormatHeatmap = "DD-MM-YYYY, dddd";
const heatmapDateFormat = "YYYY-MM-DD";

for(let page of dv.pages('"09 Daily Notes"').where(p => p["5x_Salah"])) {
    try {
        const dateMoment = moment(page.file.name, filenameDateFormatHeatmap);

        if (dateMoment.isValid()) {
            const formattedDate = dateMoment.format(heatmapDateFormat);

            // --- INTENSITY FIX ---
            let intensityValue = typeof p["5x_Salah"] === 'number' && p["5x_Salah"] >= 1 && p["5x_Salah"] <= calendarData.intensityScaleEnd
                                 ? p["5x_Salah"]
                                 : 1; // Default to 1

            calendarData.entries.push({
                date: formattedDate,
                intensity: intensityValue, // Use the potentially adjusted intensity
            });
        } else {
             console.warn(`Could not parse date from filename for heatmap: ${page.file.name}`);
        }
    } catch (e) {
        console.error(`Error processing page ${page.file.name} for heatmap:`, e);
    }
}

renderHeatmapCalendar(this.container, calendarData)
```

```dataviewjs
// --- Calculate Mindful-Eating Streak ---
// Streak calculation remains the same as the previous corrected version
let currentStreak = 0;
try {
    const eatingPages = dv.pages('"09 Daily Notes"')
        .where(p => p["Mindful-Eating"])
        .sort(p => p.file.name, 'desc');
    const filenameDateFormatStreak = "DD-MM-YYYY, dddd";
    const eatingDates = new Set(eatingPages.map(p => p.file.name));
    let checkDate = moment();
    if (!eatingDates.has(checkDate.format(filenameDateFormatStreak))) {
         checkDate.subtract(1, 'day');
         if (!eatingDates.has(checkDate.format(filenameDateFormatStreak))) {
             checkDate = null;
         }
    }
    if (checkDate) {
        while (eatingDates.has(checkDate.format(filenameDateFormatStreak))) {
            currentStreak++;
            checkDate.subtract(1, 'day');
        }
    }
} catch (e) {
    console.error("Error calculating Mindful-Eating streak:", e);
    currentStreak = "Error";
}

// --- Display Title with Streak ---
dv.span(`**Mindful-Eating🍎 🔥${currentStreak}**`);


// --- Calendar Code (Adjusted for Color Rendering) ---
const calendarData = {
    intensityScaleEnd: 5,
    colors: {
        red: ["#11ff00", "#11ff00", "#11ff00", "#11ff00", "#11ff00"]
    },
    entries: []
}

const filenameDateFormatHeatmap = "DD-MM-YYYY, dddd";
const heatmapDateFormat = "YYYY-MM-DD";

for(let page of dv.pages('"09 Daily Notes"').where(p => p["Mindful-Eating"])) {
    try {
        const dateMoment = moment(page.file.name, filenameDateFormatHeatmap);

        if (dateMoment.isValid()) {
            const formattedDate = dateMoment.format(heatmapDateFormat);

            // --- INTENSITY FIX ---
            let intensityValue = typeof p["Mindful-Eating"] === 'number' && p["Mindful-Eating"] >= 1 && p["Mindful-Eating"] <= calendarData.intensityScaleEnd
                                 ? p["Mindful-Eating"]
                                 : 1; // Default to 1

            calendarData.entries.push({
                date: formattedDate,
                intensity: intensityValue, // Use the potentially adjusted intensity
            });
        } else {
             console.warn(`Could not parse date from filename for heatmap: ${page.file.name}`);
        }
    } catch (e) {
        console.error(`Error processing page ${page.file.name} for heatmap:`, e);
    }
}

renderHeatmapCalendar(this.container, calendarData)
```

```dataviewjs
// --- Calculate 5K+ Steps Streak ---
// Streak calculation remains the same as the previous corrected version
let currentStreak = 0;
try {
    const stepsPages = dv.pages('"09 Daily Notes"')
        .where(p => p.Steps_5k)
        .sort(p => p.file.name, 'desc');
    const filenameDateFormatStreak = "DD-MM-YYYY, dddd";
    const stepsDates = new Set(stepsPages.map(p => p.file.name));
    let checkDate = moment();
    if (!stepsDates.has(checkDate.format(filenameDateFormatStreak))) {
         checkDate.subtract(1, 'day');
         if (!stepsDates.has(checkDate.format(filenameDateFormatStreak))) {
             checkDate = null;
         }
    }
    if (checkDate) {
        while (stepsDates.has(checkDate.format(filenameDateFormatStreak))) {
            currentStreak++;
            checkDate.subtract(1, 'day');
        }
    }
} catch (e) {
    console.error("Error calculating Steps_5k streak:", e);
    currentStreak = "Error";
}

// --- Display Title with Streak ---
dv.span(`**5K+ Steps🚶 🔥${currentStreak}**`);


// --- Calendar Code (Adjusted for Color Rendering) ---
const calendarData = {
    intensityScaleEnd: 5,
    colors: {
        red: ["#f3ff00", "#f3ff00", "#f3ff00", "#f3ff00", "#f3ff00"]
    },
    entries: []
}

const filenameDateFormatHeatmap = "DD-MM-YYYY, dddd";
const heatmapDateFormat = "YYYY-MM-DD";

for(let page of dv.pages('"09 Daily Notes"').where(p => p.Steps_5k)) {
    try {
        const dateMoment = moment(page.file.name, filenameDateFormatHeatmap);

        if (dateMoment.isValid()) {
            const formattedDate = dateMoment.format(heatmapDateFormat);

            // --- INTENSITY FIX ---
            let intensityValue = typeof p.Steps_5k === 'number' && p.Steps_5k >= 1 && p.Steps_5k <= calendarData.intensityScaleEnd
                                 ? p.Steps_5k
                                 : 1; // Default to 1

            calendarData.entries.push({
                date: formattedDate,
                intensity: intensityValue, // Use the potentially adjusted intensity
            });
        } else {
             console.warn(`Could not parse date from filename for heatmap: ${page.file.name}`);
        }
    } catch (e) {
        console.error(`Error processing page ${page.file.name} for heatmap:`, e);
    }
}

renderHeatmapCalendar(this.container, calendarData)
```

```dataviewjs
// --- Calculate Sleep-on-Time Streak ---
// Streak calculation remains the same as the previous corrected version
let currentStreak = 0;
try {
    const sleepPages = dv.pages('"09 Daily Notes"')
        .where(p => p["Sleep-on-Time"])
        .sort(p => p.file.name, 'desc');
    const filenameDateFormatStreak = "DD-MM-YYYY, dddd";
    const sleepDates = new Set(sleepPages.map(p => p.file.name));
    let checkDate = moment();
    if (!sleepDates.has(checkDate.format(filenameDateFormatStreak))) {
         checkDate.subtract(1, 'day');
         if (!sleepDates.has(checkDate.format(filenameDateFormatStreak))) {
             checkDate = null;
         }
    }
    if (checkDate) {
        while (sleepDates.has(checkDate.format(filenameDateFormatStreak))) {
            currentStreak++;
            checkDate.subtract(1, 'day');
        }
    }
} catch (e) {
    console.error("Error calculating Sleep-on-Time streak:", e);
    currentStreak = "Error";
}

// --- Display Title with Streak ---
dv.span(`**Sleep-on-Time😴 🔥${currentStreak}**`);


// --- Calendar Code (Adjusted for Color Rendering) ---
const calendarData = {
    intensityScaleEnd: 5,
    colors: {
        red: ["#2e00ff", "#2e00ff", "#2e00ff", "#2e00ff", "#2e00ff"]
    },
    entries: []
}

const filenameDateFormatHeatmap = "DD-MM-YYYY, dddd";
const heatmapDateFormat = "YYYY-MM-DD";

for(let page of dv.pages('"09 Daily Notes"').where(p => p["Sleep-on-Time"])) {
    try {
        const dateMoment = moment(page.file.name, filenameDateFormatHeatmap);

        if (dateMoment.isValid()) {
            const formattedDate = dateMoment.format(heatmapDateFormat);

            // --- INTENSITY FIX ---
            let intensityValue = typeof p["Sleep-on-Time"] === 'number' && p["Sleep-on-Time"] >= 1 && p["Sleep-on-Time"] <= calendarData.intensityScaleEnd
                                 ? p["Sleep-on-Time"]
                                 : 1; // Default to 1

            calendarData.entries.push({
                date: formattedDate,
                intensity: intensityValue, // Use the potentially adjusted intensity
            });
        } else {
             console.warn(`Could not parse date from filename for heatmap: ${page.file.name}`);
        }
    } catch (e) {
        console.error(`Error processing page ${page.file.name} for heatmap:`, e);
    }
}

renderHeatmapCalendar(this.container, calendarData)
```

```dataviewjs
// --- Calculate Stress Streak ---
// Streak calculation remains the same as the previous corrected version
let currentStreak = 0;
try {
    const stressPages = dv.pages('"09 Daily Notes"')
        .where(p => p.Stress)
        .sort(p => p.file.name, 'desc');
    const filenameDateFormatStreak = "DD-MM-YYYY, dddd";
    const stressDates = new Set(stressPages.map(p => p.file.name));
    let checkDate = moment();
    if (!stressDates.has(checkDate.format(filenameDateFormatStreak))) {
         checkDate.subtract(1, 'day');
         if (!stressDates.has(checkDate.format(filenameDateFormatStreak))) {
             checkDate = null;
         }
    }
    if (checkDate) {
        while (stressDates.has(checkDate.format(filenameDateFormatStreak))) {
            currentStreak++;
            checkDate.subtract(1, 'day');
        }
    }
} catch (e) {
    console.error("Error calculating Stress streak:", e);
    currentStreak = "Error";
}

// --- Display Title with Streak ---
dv.span(`**Stress🤯 🔥${currentStreak}**`); // Or use ⚠️ icon if preferred


// --- Calendar Code (Adjusted for Color Rendering) ---
const calendarData = {
    intensityScaleEnd: 5,
    colors: {
        red: ["#ff7400", "#ff7400", "#ff7400", "#ff7400", "#ff7400"]
    },
    entries: []
}

const filenameDateFormatHeatmap = "DD-MM-YYYY, dddd";
const heatmapDateFormat = "YYYY-MM-DD";

for(let page of dv.pages('"09 Daily Notes"').where(p => p.Stress)) {
    try {
        const dateMoment = moment(page.file.name, filenameDateFormatHeatmap);

        if (dateMoment.isValid()) {
            const formattedDate = dateMoment.format(heatmapDateFormat);

            // --- INTENSITY FIX ---
            let intensityValue = typeof p.Stress === 'number' && p.Stress >= 1 && p.Stress <= calendarData.intensityScaleEnd
                                 ? p.Stress
                                 : 1; // Default to 1

            calendarData.entries.push({
                date: formattedDate,
                intensity: intensityValue, // Use the potentially adjusted intensity
            });
        } else {
             console.warn(`Could not parse date from filename for heatmap: ${page.file.name}`);
        }
    } catch (e) {
        console.error(`Error processing page ${page.file.name} for heatmap:`, e);
    }
}

renderHeatmapCalendar(this.container, calendarData)
```

```dataviewjs
// --- Calculate NNN Streak ---
// Streak calculation remains the same as the previous corrected version
let currentStreak = 0;
try {
    const nnnPages = dv.pages('"09 Daily Notes"')
        .where(p => p.NNN)
        .sort(p => p.file.name, 'desc');
    const filenameDateFormatStreak = "DD-MM-YYYY, dddd";
    const nnnDates = new Set(nnnPages.map(p => p.file.name));
    let checkDate = moment();
    if (!nnnDates.has(checkDate.format(filenameDateFormatStreak))) {
         checkDate.subtract(1, 'day');
         if (!nnnDates.has(checkDate.format(filenameDateFormatStreak))) {
             checkDate = null;
         }
    }
    if (checkDate) {
        while (nnnDates.has(checkDate.format(filenameDateFormatStreak))) {
            currentStreak++;
            checkDate.subtract(1, 'day');
        }
    }
} catch (e) {
    console.error("Error calculating NNN streak:", e);
    currentStreak = "Error";
}

// --- Display Title with Streak ---
dv.span(`**NNN⛓️ 🔥${currentStreak}**`);


// --- Calendar Code (Adjusted for Color Rendering) ---
const calendarData = {
    // intensityScaleEnd: 1, // Set scale end to 1 if using fixed intensity
    // OR keep intensityScaleEnd: 5 if p.NNN *can* be 1-5, see note below
    intensityScaleEnd: 5, // Keep original for now, assuming NNN might be 1-5
    colors: {
        // Using 'red' key as before. If this still fails, try 'default' or consult library docs.
        red: ["#00ffc9", "#00ffc9", "#00ffc9", "#00ffc9", "#00ffc9"]
        // If using fixed intensity 1, simplify: red: ["#00ffc9"]
    },
    entries: []
}

const filenameDateFormatHeatmap = "DD-MM-YYYY, dddd";
const heatmapDateFormat = "YYYY-MM-DD";

for(let page of dv.pages('"09 Daily Notes"').where(p => p.NNN)) {
    try {
        const dateMoment = moment(page.file.name, filenameDateFormatHeatmap);

        if (dateMoment.isValid()) {
            const formattedDate = dateMoment.format(heatmapDateFormat);

            // --- INTENSITY FIX ---
            // Check if p.NNN is a number between 1 and 5. If not, default to 1.
            let intensityValue = typeof p.NNN === 'number' && p.NNN >= 1 && p.NNN <= calendarData.intensityScaleEnd
                                 ? p.NNN
                                 : 1; // Default to 1 if p.NNN is true/checkbox/non-numeric

            calendarData.entries.push({
                date: formattedDate,
                intensity: intensityValue, // Use the potentially adjusted intensity
            });
        } else {
             console.warn(`Could not parse date from filename for heatmap: ${page.file.name}`);
        }
    } catch (e) {
        console.error(`Error processing page ${page.file.name} for heatmap:`, e);
    }
}

renderHeatmapCalendar(this.container, calendarData)
```

```dataviewjs
// --- Calculate Skincare Streak ---
let currentStreak = 0;
try {
    // Get pages with the 'Skincare' field, sort by date descending
    const skincarePages = dv.pages('"09 Daily Notes"')
        .where(p => p.Skincare) // Check if 'Skincare' exists and is truthy
        .sort(p => p.file.name, 'desc'); // Sort by filename (date) descending

    // Define the format your filenames are *currently* in for streak calculation
    const filenameDateFormatStreak = "DD-MM-YYYY, dddd";

    // Create a Set of tracked dates (using the actual filename format) for fast lookup
    const skincareDates = new Set(skincarePages.map(p => p.file.name));

    // Calculate streak starting from today/yesterday
    let checkDate = moment(); // Use moment.js

    // Check if today or yesterday was the last day to start the streak count
    if (!skincareDates.has(checkDate.format(filenameDateFormatStreak))) {
        // Didn't complete today, check yesterday
         checkDate.subtract(1, 'day');
         if (!skincareDates.has(checkDate.format(filenameDateFormatStreak))) {
             // Didn't complete yesterday either, streak is 0
             checkDate = null; // Signal streak is 0
         }
    }
    // else: Completed today, checkDate remains today.

    // If we have a valid starting point (today or yesterday completed)
    if (checkDate) {
        while (skincareDates.has(checkDate.format(filenameDateFormatStreak))) {
            currentStreak++;
            checkDate.subtract(1, 'day'); // Move to check the previous day
        }
    }
    // If checkDate was null, currentStreak remains 0

} catch (e) {
    console.error("Error calculating Skincare streak:", e);
    currentStreak = "Error"; // Indicate error state
}

// --- Display Title with Streak ---
dv.span(`**Skincare💟 🔥${currentStreak}**`);


// --- Calendar Code (Adjusted for Color Rendering) ---
const calendarData = {
    intensityScaleEnd: 5,
    colors: {
        // Using 'red' key as in original. Change key if needed by library.
        red: ["#c9ff00", "#c9ff00", "#c9ff00", "#c9ff00", "#c9ff00"]
    },
    entries: []
}

// Define the format your filenames are *currently* in
const filenameDateFormatHeatmap = "DD-MM-YYYY, dddd";
// Define the format the heatmap library likely expects
const heatmapDateFormat = "YYYY-MM-DD";

for(let page of dv.pages('"09 Daily Notes"').where(p => p.Skincare)) {
    try {
        // Parse the date from the filename using its specific format
        const dateMoment = moment(page.file.name, filenameDateFormatHeatmap);

        // Check if the date was parsed successfully
        if (dateMoment.isValid()) {
            // Format the date into the standard YYYY-MM-DD format for the heatmap
            const formattedDate = dateMoment.format(heatmapDateFormat);

            // --- INTENSITY FIX ---
            let intensityValue = typeof p.Skincare === 'number' && p.Skincare >= 1 && p.Skincare <= calendarData.intensityScaleEnd
                                 ? p.Skincare
                                 : 1; // Default to 1

            calendarData.entries.push({
                date: formattedDate, // Use the CORRECTLY FORMATTED date here
                intensity: intensityValue, // Use the potentially adjusted intensity
                // No 'content' property
            });
        } else {
             // Optional: Log a warning if a filename couldn't be parsed
             console.warn(`Could not parse date from filename for heatmap: ${page.file.name}`);
        }
    } catch (e) {
        console.error(`Error processing page ${page.file.name} for heatmap:`, e);
    }
}

// Render the heatmap
renderHeatmapCalendar(this.container, calendarData)
```

```dataviewjs
// --- Calculate Hair-Oil Streak ---
let currentStreak = 0;
try {
    // Get pages with the 'Hair_Oil' field, sort by date descending
    const hairOilPages = dv.pages('"09 Daily Notes"')
        .where(p => p["Hair_Oil"]) // Use bracket notation for field name
        .sort(p => p.file.name, 'desc'); // Sort by filename (date) descending

    // Define the format your filenames are *currently* in for streak calculation
    const filenameDateFormatStreak = "DD-MM-YYYY, dddd";

    // Create a Set of tracked dates (using the actual filename format) for fast lookup
    const hairOilDates = new Set(hairOilPages.map(p => p.file.name));

    // Calculate streak starting from today/yesterday
    let checkDate = moment(); // Use moment.js

    // Check if today or yesterday was the last day to start the streak count
    if (!hairOilDates.has(checkDate.format(filenameDateFormatStreak))) {
        // Didn't complete today, check yesterday
         checkDate.subtract(1, 'day');
         if (!hairOilDates.has(checkDate.format(filenameDateFormatStreak))) {
             // Didn't complete yesterday either, streak is 0
             checkDate = null; // Signal streak is 0
         }
    }
    // else: Completed today, checkDate remains today.

    // If we have a valid starting point (today or yesterday completed)
    if (checkDate) {
        while (hairOilDates.has(checkDate.format(filenameDateFormatStreak))) {
            currentStreak++;
            checkDate.subtract(1, 'day'); // Move to check the previous day
        }
    }
    // If checkDate was null, currentStreak remains 0

} catch (e) {
    console.error("Error calculating Hair_Oil streak:", e);
    currentStreak = "Error"; // Indicate error state
}

// --- Display Title with Streak ---
dv.span(`**Hair-Oil💇‍♂️ 🔥${currentStreak}**`);


// --- Calendar Code (Adjusted for Color Rendering) ---
const calendarData = {
    intensityScaleEnd: 5,
    colors: {
        // Using 'red' key as in original. Change key if needed by library.
        red: ["#ff0023", "#ff0023", "#ff0023", "#ff0023", "#ff0023"]
    },
    entries: []
}

// Define the format your filenames are *currently* in
const filenameDateFormatHeatmap = "DD-MM-YYYY, dddd";
// Define the format the heatmap library likely expects
const heatmapDateFormat = "YYYY-MM-DD";

for(let page of dv.pages('"09 Daily Notes"').where(p => p["Hair_Oil"])) { // Use bracket notation
    try {
        // Parse the date from the filename using its specific format
        const dateMoment = moment(page.file.name, filenameDateFormatHeatmap);

        // Check if the date was parsed successfully
        if (dateMoment.isValid()) {
            // Format the date into the standard YYYY-MM-DD format for the heatmap
            const formattedDate = dateMoment.format(heatmapDateFormat);

            // --- INTENSITY FIX ---
            let intensityValue = typeof p["Hair_Oil"] === 'number' && p["Hair_Oil"] >= 1 && p["Hair_Oil"] <= calendarData.intensityScaleEnd
                                 ? p["Hair_Oil"]
                                 : 1; // Default to 1

            calendarData.entries.push({
                date: formattedDate, // Use the CORRECTLY FORMATTED date here
                intensity: intensityValue, // Use the potentially adjusted intensity
                // No 'content' property
            });
        } else {
             // Optional: Log a warning if a filename couldn't be parsed
             console.warn(`Could not parse date from filename for heatmap: ${page.file.name}`);
        }
    } catch (e) {
        console.error(`Error processing page ${page.file.name} for heatmap:`, e);
    }
}

// Render the heatmap
renderHeatmapCalendar(this.container, calendarData)
```
