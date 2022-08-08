# Reguliere expressies

1.  Geef een reguliere expressie waarmee je elke regel selecteert waar aan het eind van de regel een punt (`.`) staat.

    <textarea name="form[q1]" rows="2" required></textarea>

2.  Geef een reguliere expressie waarmee je elke regel selecteert waarin de string `the` (of `The`) staat. `There is nothing.` moet ook matchen.

    <textarea name="form[q2]" rows="2" required></textarea>

3.  Geef een reguliere expressie waarmee je elke regel selecteert waarin het woord (dus niet de string) `we` staat.

    <textarea name="form[q3]" rows="2" required></textarea>

4.  Geef een reguliere expressie waarmee je elke regel selecteert die met `A`, `D` of `W` begint.

    <textarea name="form[q4]" rows="2" required></textarea>

5.  Geef een reguliere expressie waarmee je elke regel selecteert waarin een `o` staat gevolgd door één of meer `r`.

    <textarea name="form[q5]" rows="2" required></textarea>

6.  Geef een reguliere expressie waarmee je elke regel selecteert waarin een vraagteken óf een backslash staan.

    <textarea name="form[q6]" rows="2" required></textarea>

https://leanpub.com/bastards-regexes
https://algs4.cs.princeton.edu/54regexp/
https://v4.software-carpentry.org/regexp/index.html
Let's start by getting a wordlist. Install "aspell" using brew or apt-get. Then run the following command to generate a word list file for Dutch:
aspell -d nl dump master | aspell -l nl expand > woorden.txt
Use "head" and "tail" to inspect the file. It's huge, so using "head" helps us to get a small sample.
Now we are going to use grep to find words in the list.
grep "doos" < woorden.txt
What is the result? All words that contain the string "doos".
We can also grep for words that start with the string "doos":
grep "^doos" < woorden.txt
How many are there? (wc)
And to grep words that end with the string "doos", we use:
grep "doos$" < woorden.txt
How many are there?
Now combine both to find the word "doos" itself.
grep "^doos$" < woorden.txt
In all the commands above, we use the fact that the word list is organized to have 1 word per line. This works because grep is a line-based search tool. grep will "match" every line that conforms to the search string we enter and print the entire line. We use the special characters ^ and $ to signify the "start of the line" and "end of the line" respectively. So ^doos matches "any line that starts with the string doos". In practice this yields all words that start with doos.
Using this technique we now have a way of finding words in the word list. What happens if the word that we want to find is not in the list? Try it for yourself.
We will now introduce a special character "." that is used to match any character on the line. Let's search word a puzzle word. It has 9 letters and the second and third letters are "bd". What could it be?
grep "^.bd......$" woorden.txt
Only 8 matches! We'll be solving that puzzle soon.
