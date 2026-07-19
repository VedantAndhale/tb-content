---
title: Summary of books
---
```dataviewjs
const books = dv.pages("#book");

dv.table(
    ["Book", "Notes"],
    books.map(book => {
        const folder = book.file.folder;
        const title = folder.split("/").pop(); // last part of the folder path
        const notes = dv.pages(`"${folder}"`).length - 1;

        return [`[[${book.file.path}|${title}]]`, notes];
    })
);
```


