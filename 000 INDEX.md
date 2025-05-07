# Home 

### 🌼 Daily Notes
```dataviewjs
// 1. cutoff = midnight today minus 6 days
const cutoff = new Date();
cutoff.setHours(0,0,0,0);
cutoff.setDate(cutoff.getDate() - 6);

// 2. collect, parse, filter, sort by timestamp
const recent = dv
  .pages('"09 Daily Notes"')
  .where(p => /^\d{2}-\d{2}-\d{4}/.test(p.file.name))
  .map(p => {
    const [dd, mm, yyyy] = p.file.name.split(',')[0].split('-').map(n => +n);
    p._date = new Date(yyyy, mm - 1, dd);
    return p;
  })
  .filter(p => p._date >= cutoff)
  .sort(p => p._date.getTime(), 'desc');  // ← sort by timestamp

// 3. render
dv.table(
  ["File", "Date"],
  recent.map(p => [
    p.file.link,
    p._date.toLocaleDateString('en-GB')
  ])
);
```
### 🍉 [[A Sense of Purpose]]
### 🎯 [[Strategy]]

### 🚮 [[DUMP MOC|dump-random]] 

### Civil Services Notes📚

- [[_Anki_Collection_Index|Anki Decks🗂️]] 

- General Studies  
	- 01 – [[MOC GS1]] 
	- 02 – [[MOC GS2]]  
	- 03 – [[MOC GS3]]  
	- 04 – [[MOC GS4]]

* Essay
	- 05 - [[MOC Essay]] /

* Sociology

	- - [[MOC Socio Paper 1]]
	- - [[MOC Socio Paper 2]]

- Current Affairs  
	- - [[MOC for C.A]] 

### PYQ and Themes 🛣️

- Prelims
	1. [[Hist Ancient India]] 47 Questions
	2. [[Hist Medieval India]] 27 Questions
	3. [[Hist Art & Culture]] 33 Questions
	4. [[Hist Modern India]] 70 Questions
	5. [[Indian Geography]] 56 Questions
	6. [[World Geography]] 54 Questions
	7. [[Environment & Ecology And Disaster Management]] 98
	8. [[Polity and Governance]] 107 Questions
	9. [[International Relations]] 27 Questions
	10. [[Economy]] 300 Questions
	11. [[03 Syllabus and PYQ themes/Prelims/Science and Technology|Science and Technology]] 144 Questions
	12. [[C.A. and GK, Misc.]] 136 Questions

* Mains
	* GS : [[GS PYQ Themes]]
	* Optional: [[Socio PYQ Themes]]

---

## Important Tags 🏷️

| Emojis                      | Tags                        | Shortcut key                 |
| --------------------------- | --------------------------- | ---------------------------- |
| Important                   | #📌imp                      | Pushpin                      |
| Fact                        | #🧐fact                     | Monocle Face                 |
| Current affairs             | #ca📰                       | Newspaper                    |
| A crisp definition          | #📜definition               | Scroll                       |
| Quote                       | #✒️Quote                    | Black nib                    |
| Data and Statistics         | #📊Stats                    | Bar Chart                    |
| Schemes                     | #🆓Schemes                  | Free                         |
| To do                       | #☑️To-Do                    | Check box with check         |
| Bills and Acts              | #🎭Bills/Acts               | Performing Arts              |
| Supreme court judgements    | #🔨Judgements               | Hammer                       |
| Committee Recommendations   | #📩Committe-Recommendations | Envelope with arrow          |
| Remember/Forgetting         | #📍remember/forgetting      | Round Pushpin                |
| An introduction to remember | #🧠Introduction             | Brain                        |
| A conclusion to remember    | #😎Conclusion               | Smiling face with sunglasses |
| Concept                     | #🍪Concept                  | Cookie                       |
| GS1                         | #GS1️⃣                      | One                          |
| GS2                         | #GS2️⃣                      | Two                          |
| GS3                         | #GS3️⃣                      | Three                        |
| GS4                         | #GS4️⃣                      | Four                         |
| Strategy                    | #🤔Plan                     | Thinking face                |
| Modern History              | #MH🥳                       | Partying face                |
| Ancient, Medieval, A&C      | #AMAC🧓                     | old man                      |
| Geography                   | #Geo🌍                      | globe                        |
| Sociology and Society       | #🫂Socio                    | People Hugging               |
| Polity                      | #Pol⚖️                      | balance scale                |
| Governance                  | #Governance👮               | Police                       |
| International Relations     | #IR🌐                       | globe w meridians            |
| Agri                        | #Agri🧺                     | Basket                       |
| Disaster Management         | #DisasterM🌀                | Cyclone                      |
| Economics                   | #💵Eco                      | Dollar blank Note            |
| Environment                 | #🐄Environment              | Cow                          |
| Internal Security           | #😨InternalSecurity         | Fearful Face                 |
| Science and Tech            | #Science-tech🔬             | Microscope                   |
| Ethics Examples             | #Ethics-Examples😇          | Angel                        |
| Productivity and tools      | #productivity-and-tech🗑️   | waste                        |
| Mapping                     | #map🗺️                     | world map                    |
| Essay-fodder                | #essay🖇️                   | Linked paperclips            |
| CSAT                        | #csat🔢                     | Numbers                      |
| World History               | #WorldHistory👵             | Old Woman                    |
| Post Independence           | #postIndp🏳️                | White Flag                   |
