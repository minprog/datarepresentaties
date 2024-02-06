# Oefeningen

Deze vragen zijn goede oefeningen voor het tentamen. De verwachting is dat je alle vragen op het tentamen correct beantwoordt, foutjes daargelaten. Je hebt dus parate kennis nodig van de commando's en wat ze doen. Als je merkt dat je deze kennis nog niet echt paraat hebt, dan kun je extra studeren met hulp van de Software Carpentry-workshop en de andere materialen.

## Parate kennis

Wat je zeker moet weten voor het tentamen:

- De werking van onderstaande commando's en een aantal specifieke opties.
- Hoe paths werken als verwijzing naar bestanden en directories in het file system.
- Hoe wildcards werken om meerdere bestanden te "matchen".

<!-- ## Overzicht behandelde commando's

Algemeen:

- man

Navigatie door directories:

- ls, ls --help, ls -F, ls -l, ls -h, ls -r, ls -t
- pwd
- cd, cd -, cd ..

Files en directories manipuleren:

- mkdir, mkdir -p
- touch
- mv
- cp, cp -r
- rm, rm -i, rm -r

Data processing:

- wc, wc -l
- sort, sort -n, sort -r
- head, head -n
- echo
- tail, tail -n
- cut, cut -d, cut -f
- uniq, uniq -c
- cat -->

## Opgaven over commando's

Beantwoord de volgende vragen. Geef altijd een concreet en compleet commando. Als er geen file- of directorynaam is opgegeven moet je zelf een naam verzinnen.

1. Wat is het commando om de man-pagina van een bepaald programma te openen in de terminal?
1. Welk commando gebruik je om de inhoud van een map weer te geven, inclusief datum en grootte?
1. Wat is het commando om de huidige locatie in het bestandssysteem weer te geven?
1. Hoe verander je de huidige locatie naar een andere map?
1. Wat is het commando om een nieuwe map aan te maken in de huidige locatie?
1. Hoe maak je een nieuw leeg bestand aan met de naam `gegevens.dat`?
1. Hoe verplaats je een bestand naar de directory `data` met het mv-commando?
1. Wat is het commando om hele map te kopiëren naar een andere locatie?
1. Hoe verwijder je een bestand?

Er zijn nog veel meer vragen mogelijk. Je kunt de Software Carpentry-workshop uitpluizen om goed voorbereid te zijn. Maak zelf een overzicht van behandelde commando's en opties.

## Opgaven met paths

Het commando `cat` is een van de simpelste: het kan de inhoud van een tekstbestand weergeven. Je gebruikt bijvoorbeeld `cat bestandsnaam.txt`. Geef hieronder commando's om een bestand te `cat`ten, dus de inhoud op het scherm te printen. Enkele notities om de vraagstelling goed te begrijpen:

- Als je `cd` gebruikt om naar een directory te "gaan" dan "ben je in de directory", of eigenlijk is de shell in die directory.
- Een relatief pad begint nooit met een `/`. Dat is het hele idee. Begrijp je dit nog niet, lees dan het hoofdstuk, de uitleg van Software Carpentry, of bespreek met je medestudenten.

De opgaven:

1. Hoe `cat` je een file `/Users/martijn/kattennamen.txt` als je in de directory `/Users/martijn` bent met hulp van een zo kort mogelijk *relatief* pad?
1. Hoe `cat` je een file `/Users/martijn/kattennamen.txt` als je in de directory `/Users/jelle` bent met hulp van een zo kort mogelijk *relatief* pad?
1. Hoe `cat` je een file `/Users/martijn/kattennamen.txt` als je in de directory `/mnt/server2` bent met hulp van een zo kort mogelijk *relatief* pad?
1. Hoe `cat` je een file `/Users/martijn/kattennamen.txt` als je in de directory `/` bent met hulp van een zo kort mogelijk *relatief* pad?
1. Hoe `cat` je een file `kattennamen.txt` in de directory `/Users/martijn` met hulp van een absoluut pad?
1. Hoe `cat` je een file `kattennamen.txt` in de directory `/root` met hulp van een absoluut pad?

## Nakijken

Deze oefeningen kun je niet inleveren. Je kunt je uitwerkingen zelf controleren door alles uit te proberen in een UNIX-shell. Maak de bestanden aan zoals genoemd en kijk of het lukt. Daarnaast kun je je antwoorden vergelijken met die van je buren.

Voorbeeldantwoord vraag 2: `cat ../martijn/kattennamen.txt`.
