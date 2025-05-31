```dataviewjs
const subjectTags = ["History", "Geography", "Polity", "Society", "IR", "S&T", "Environment", "Ethics"];
const relevanceTags = ["Prelims", "Essay", "Optional", "GS1", "GS2", "GS3", "GS4"];
// **IMPORTANT**: Confirm this is the correct path from your vault root to your notes
const folderPath = "Notes/01 Current Affairs/Current Affairs";

let pages = dv.pages(`"${folderPath}"`)
    .where(p => p.file.name !== dv.current().file.name) // Exclude the current file
    .sort(p => p.file.name, 'asc'); // Sort by file name ascending

if (pages.length > 0) {
    dv.table(
        ["Name", "Subject", "Topic", "Relevance", "Syllabus Link"],
        pages.map(p => {
            // Get all tags from the file (they include the '#' prefix)
            // and remove the '#' prefix for comparison and display
            const allPageTags = p.file.tags ? p.file.tags.map(tag => tag.substring(1)) : [];

            const pageSubject = allPageTags.filter(tag => subjectTags.includes(tag));
            const pageRelevance = allPageTags.filter(tag => relevanceTags.includes(tag));
            const pageTopic = allPageTags.filter(tag => 
                !subjectTags.includes(tag) && 
                !relevanceTags.includes(tag)
            );

            return [
                p.file.link,
                pageSubject, // dv.table will display arrays nicely
                pageTopic,
                pageRelevance,
                p.file.outlinks // This is already an array of links
            ];
        })
    );
} else {
    dv.paragraph("DataviewJS: No results to show for table query. Check folder path and note content.");
}
```