---
title: Summary of books
---
```dataview
const books = dv.pages("#book");

dv.table(
    ["Book", "Notes"],
    books.map(book => {
        const notes = dv.pages(`"${book.file.folder}"`).length - 1;
        return [book.file.link, notes];
    })
);
```
