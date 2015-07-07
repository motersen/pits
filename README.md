# pits

## What?

Pits lets you keep your files organized and find what you're looking for
immediately by tagging them so you can be the first to post that image
macro. Fast and simple.

Tags are created as you use them, just as files are added when you tag
them. And when you don't need a tag anymore (or remove all tags from a
file) pits forgets about it automatically. The data is kept in a
PicoLisp pool database in the directory you invoke pits in. This, and
the fact that filenames are kept as relative paths means you can just
copy your files and the database (.pitsdb) and keep all your tags.

## How?

### Installation

You only need a picolisp interpreter and the pits script somewhere in
your `PATH`. Then you can run pits as follows:

### Using

- pits **af|all-files**
- pits **at|all-tags**
- pits **gc**
- pits **lf|list-files** &lt;tag&gt;
- pits **lt|list-tags** &lt;file&gt;
- pits **rm|remove** "tag|tags" &lt;tag&gt;...
- pits **rm|remove** "file|files" &lt;file&gt;...
- pits **t|tag** &lt;file&gt; &lt;tag&gt;...
- pits **tf|tag-files** &lt;tag&gt; &lt;file&gt;...
- pits **ut|untag** &lt;file&gt; &lt;tag&gt;...
- pits **utf|untag-files** &lt;tag&gt; &lt;file&gt;...

**af, all-files**

Prints all files tagged in the local database in alphabetical order.

---

**at, all-tags**

Prints all tags used in the local database in alphabetical order.

---

**gc**

Removes all files from the database that no longer exist.

---

**lf, list-files &lt;tag&gt;**

Prints all files tagged with &lt;tag&gt; in alphabetical order.

---

**lt, list-tags &lt;file&gt;**

Prints all tags added to &lt;file&gt; in alphabetical order.

---

**rm "tag|tags" &lt;tag&gt;...**

Removes one or more tags from the database after untagging all related
files.

**rm "file|files" &lt;file&gt;...**

Removes one or more files from the database after untagging them.

---

**t, tag &lt;file&gt; &lt;tag&gt;...**

Adds one or more tags to &lt;file&gt;. If &lt;file&gt; is not already in
the database, pits checks if it exists and, if so, registers it in the
database. Tags are created if they don't exist yet.

**tf, tag-files &lt;tag&gt; &lt;file&gt;...**

Adds &lt;tag&gt; to one or more files. Basically the same behaviour as
**tag**, but reversed.

---

**ut, untag &lt;file&gt; &lt;tag&gt;...**

Counterpart to **tag**. Removes one or more tags from &lt;file&gt;.

**utf, untag-files &lt;tag&gt; &lt;file&gt;...**

Counterpart to **tag-files**. Removes &lt;tag&gt; from one or more
files.

### ...that's all  ?

More functionality is coming - here's the list:

- [x] Removing tags from files
- [ ] Narrowing the output of list-{files|tags} by combining the sets of
      tagged images using (and), (or), (not)...	
- [ ] A mv command to rename a file in pits and the filesystem
- [ ] Reading input from pipes
