# CSV-formaat

Simplest way to organize data in text files. Data is tabular, i.e. there are rows and columns. A row is sometimes called a tuple. A column is sometimes called a field.
Values in a row are separated by a separator character. Rows are separated by newline characters.
Often-used separator characters are comma (,) or tab (TSV).
Values may contain newlines. But how do you deal with that when reading the file? Values may be contained in double quotes. When reading in CSV values with double quotes, these quotes are not represented in the data.

See https://creativyst.com/Doc/Articles/CSV/CSV01.shtml
https://github.com/dbro/csvquote

Sort using command-line args -k (sort key fields??) and -t (field separator)

Assignment: fix a malformed CSV file until it reads in well???
