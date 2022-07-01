# Week 4: Structured text

Chapter 13 Bulletproof UNIX

How do you put large amounts of data in files? Why would you put this in ASCII vis-à-vis a custom binary format? What is tabular data? What is hierarchical data? How can you "query" data?

## CSV

Simplest way to organize data in text files. Data is tabular, i.e. there are rows and columns. A row is sometimes called a tuple. A column is sometimes called a field.
Values in a row are separated by a separator character. Rows are separated by newline characters.
Often-used separator characters are comma (,) or tab (TSV).
Values may contain newlines. But how do you deal with that when reading the file? Values may be contained in double quotes. When reading in CSV values with double quotes, these quotes are not represented in the data.

See https://creativyst.com/Doc/Articles/CSV/CSV01.shtml
https://github.com/dbro/csvquote

Sort using command-line args -k (sort key fields??) and -t (field separator)

Assignment: fix a malformed CSV file until it reads in well???

## Awk (field-based text processing)

- https://www.gnu.org/software/gawk/manual/html_node/index.html#SEC_Contents
- https://carpentries-incubator.github.io/shell-extras/10_awk/index.html

## JSON, jq

- https://datascienceworkshops.com/blog/seven-command-line-tools-for-data-science/
- https://github.com/dbohdan/structured-text-tools
