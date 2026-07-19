---
title: Summary of books
---
[Drawing 2026-07-19 13.19.40.excalidraw.md](../Excalidraw/Drawing%202026-07-19%2013.19.40.excalidraw.md)
```dataviewjs
const books = dv.pages("#book");

dv.table(
    ["Book", "Notes"],
    books.map(book => {
        const folder = book.file.folder;
        const title = folder
            .split("/")
            .pop()
            .replace(/\s*\(\d+\)$/, ""); // Removes trailing " (1)", "(2)", etc.

        const notes = dv.pages(`"${folder}"`).length - 1;

        return [`[[${book.file.path}|${title}]]`, notes];
    })
);
```
[notitle](../Excalidraw/Drawing%202026-07-19%2013.19.40.excalidraw.md)