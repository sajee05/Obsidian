```dataview
TABLE
    file.link AS Name,
    filter(file.etags, (t) => contains(["History", "Geography", "Polity", "Society", "IR", "S&T", "Environment", "Ethics"], t)) AS Subject,
    filter(file.etags, (t) =>
        !contains(["History", "Geography", "Polity", "Society", "IR", "S&T", "Environment", "Ethics"], t) AND
        !contains(["Prelims", "Essay", "Optional", "GS1", "GS2", "GS3", "GS4"], t)
    ) AS Topic,
    filter(file.etags, (t) => contains(["Prelims", "Essay", "Optional", "GS1", "GS2", "GS3", "GS4"], t)) AS Relevance,
    file.outlinks AS "Syllabus Link"
FROM "/Notes/01 Current Affairs/Current Affairs"
WHERE file.name != this.file.name
SORT file.name ASC
```