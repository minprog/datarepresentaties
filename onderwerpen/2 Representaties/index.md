# Week 2: Representaties

Representatie van integers, floats en lettertekens. Where does it end? Which standards come in to play?

Should code == data be treated here??

Files containing plain text are nothing special. As you've learned in module 3, eventually, even text is stored in binary format, using strictly 0's and 1's.
However, plain text has a distinct place in computing because of the sheer number of applications that use plain text and because plain text files can easily be inspected by humans (in most cases). It's even possible to represent structured data using plain text files, and we'll learn more about that in the next module.

## 1.1 Overzicht Multimedia

In deze module ga je kennis maken ...

Ga naar de pagina van het [CS50-lecture over Multimedia](/cs50t/multimedia) en beantwoord alle vragen.

Onderwerpen van het college zijn:

- Representatie van tekst
- Representatie van multimedia
- Representatie van hiërarchische structuren

## 1.2 Datarepresentaties

Lees het hoofdstuk Data Storage uit het boek van Brookshear, *Computer Science: An Overview*. De onderwerpen:

- Bits and their storage
- Main memory
- Mass storage
- Representing information as bit patterns
- The binary system
- Storing integers
- Storing fractions
- Data compression
- Communication errors

Beantwoord de vragen.

[Hoofdstuk: Data, encoding and metadata](https://faculty.washington.edu/ajko/books/foundations-of-information/data)

## 1.3 ASCII vs Unicode

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

## 1.4 Het probleem met newlines

Difference between asc(10) and asc(13).

## 1.5 Woorden tellen

Modern impementations of wc work perfectly fine with UTF-8 encoded files as well as ASCII. Have a look at the `wc` man page.

What is a "word" according to the `wc` tool? Which characters are white space? -> man wc, man iswspace, man isspace, \t \n \v \f \r

Which are the options to show the number of characters vs. the number of bytes? Can you create a file using TextEdit or Notepad, save as UTF-8 and check whether wc provides different values for both counts?

Take home message: is all artificial, what counts as whitespace is just something that was defined somewhere. Some people do it differently!

## 1.6 Bestandsformaten

Uitlegvideo file formats (zowel binary als tekst)
xxd: bestuderen files in hex?
 
Opdracht: hier heb je 10 files. Wat is het FORMAAT van de file? Gebruik xxd. Hoe weet je dit? Is het een tekstformaat? Binair? Wat kun je erover vinden?
Gebruik de tool "file" om te achterhalen wat voor formaat het is.
Uitleg magic numbers



## Questions

- What would be the kinds of content of a plain text file that cannot be so easily inspected by humans?

- Decode the following ASCII message, assuming 7-bit ASCII characters and no parity: 1001010 1001111 1001000 1001110 0100000 1000100 1001111 1000101 (maybe don't use spaces!)

- The ASCII code for the letter A is 1000001, and the ASCII code for the letter a is 1100001. Given that the ASCII code for the letter G is 1000111, without looking at Table 2.7, what is the ASCII code for the letter g?
