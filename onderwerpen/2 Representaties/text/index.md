# Text encoding


Should code == data be treated here??

Files containing plain text are nothing special. As you've learned in module 3, eventually, even text is stored in binary format, using strictly 0's and 1's.
However, plain text has a distinct place in computing because of the sheer number of applications that use plain text and because plain text files can easily be inspected by humans (in most cases). It's even possible to represent structured data using plain text files, and we'll learn more about that in the next module.

## Unicode

In het boek staat dat Unicode altijd 16 bits is. Maar dat is niet waar.

<https://www.youtube.com/watch?v=MijmeoH9LT4> (computerphile ascii/Unicode)

Many plain text files are encoded using ASCII. ASCII allocates exactly 7 or 8 bits per character.  This leaves us with 128 or 256 distinct different characters that may be represented.
Original ASCII is 7 bits and contains mostly alphanumerical letters that are relevant to US English language (no accents!). 
Extended ASCII is 8 bits and contains many characters from the "eastern European" character sets. But it does not contain any characters from East Asian languages, for example.
In the case of 8 bits, the number of bytes in the file is also the number of characters!
ASCII also contains various kinds of control codes, or "unprintable characters". We'll look at those in the next modules.
ASCII can be seen as a compromise: make computers usable for processing texts while keeping the encoding simple and the use of memory reasonable. Unicode is a more modern invention and is much more ambitious than ASCII: it aims to represent as many human scripts as possible (currently 159), as well as various kinds of symbols. Currently, there are around 100.000 characters in Unicode, and the number is increasing every year.
Unicode text are saved in files using UTF-8 (or other) encoding. Here, every character does not take the same number of bits. UTF-8 assigns characters 1 or more bytes. A character encoded in 2 or more bytes is called a "multi-byte" character.
The nice thing is that the first 128 characters are encoded exactly as they are in ASCII. The very first bit in a byte is always 0 in those cases. The remaining 7 bits are used to encode a character. Only characters starting with a 1 will be interpreted differently. This means that every ASCII text (but not extended ASCII) is valid UTF-8. In other words, many files can be read assuming that they are interpretable as UTF-8.
However, every UTF-8 file is not necessarily valid ASCII. This becomes a problem in older text editors that do not expect UTF-8 text. It also becomes a problem in tools to process text written using for example Python version 2.x.
Because of this, encodings can be a bit of a hassle. It's good to be aware of this. In this course, we will notify you in case encodings may become a problem.

🌵 Oefening: een aantal tekstbestanden. Vogel uit welke encoding gebruikt is. Geef aan waarom je tot die conclusie komt.


## Het probleem met newlines

Difference between asc(10) and asc(13).

## Woorden tellen

Modern impementations of wc work perfectly fine with UTF-8 encoded files as well as ASCII. Have a look at the `wc` man page.

What is a "word" according to the `wc` tool? Which characters are white space? -> man wc, man iswspace, man isspace, \t \n \v \f \r

Which are the options to show the number of characters vs. the number of bytes? Can you create a file using TextEdit or Notepad, save as UTF-8 and check whether wc provides different values for both counts?

Take home message: is all artificial, what counts as whitespace is just something that was defined somewhere. Some people do it differently!
