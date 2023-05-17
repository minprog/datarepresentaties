# UNIX-commando's

1. Studeer in het hieronder genoemde hoofdstuk en doe de oefeningen,
2. hou goed bij wat je opvalt en wat je leert,
3. en beantwoord dan de vragen hieronder.

## Over het CSV-formaat

CSV is de simpelste manier om data te organiseren in een tekstbestand. Als de data een **tabel** is, dus als deze bestaat uit rijen en kolommen, dan kan CSV gebruikt worden om de data te organiseren.

De precieze definitie van het **Comma Separated Values** CSV-formaat is te vinden in een RFC-document. Zo'n RFC-document is een manier om een breed gebruikte werkwijze of bestandsformaat vast te leggen.

<https://datatracker.ietf.org/doc/html/rfc4180>

Let even op de terminologie. Een rij wordt ook wel een **record** genoemd. Elk record bevat alle gegevens van één ding. Een kolom wordt ook wel een **field** genoemd. Elk field is één soort gegeven, bijvoorbeeld een naam of een telefoonnummer.

Let op dat er ook nog andere formaten zijn zoals "tab separated values", die op een andere manier worden opgemaakt. Het idee is hetzelfde, maar je moet er rekening mee houden dat je zelf moet controleren of je commando's nog kloppen.

🌵 **Vraag 0.** Hieronder vind je de tekst van een CSV-bestand. Gebruik het `sort`-commando om het te sorteren op kamernummer. Standaard sorteert het commando alle regels op alfabet. Gebruik `man sort` om te achterhalen hoe je moet sorteren met velden (fields) en hoe je zorgt dat de komma wordt gebruikt om de twee velden te onderscheiden.

    Stegeman,L0.11
    van Assema,L0.09
    Vrielink,L0.10

Welk commando heb je uiteindelijk gebruikt? Leg uit hoe alle opties werken om het juiste resultaat te krijgen.

## Encodings

Ook CSV-bestanden kunnen in verschillende encodings worden opgeslagen, dus niet alleen ASCII (zoals in de RFC staat) maar bijvoorbeeld ook UTF-8. Net als bij andere teksten is het niet altijd vooraf duidelijk welke encoding wordt gebruikt. Daarom kun je bij het inlezen vaak aangeven welke encoding het moet zijn. Zie bijvoorbeeld [deze pagina met instructies over het importeren van UTF-8 CSV-bestanden in Excel](https://www.nextofwindows.com/how-to-display-csv-files-with-unicode-utf-8-encoding-in-excel). Dit is ook relevant als je geautomatiseerd data gaat verwerken; je moet dan zorgen dat je meerdere formaten aankunt, of dat alle data gegarandeerd in hetzelfde formaat wordt aangeleverd.

## Quotes

Nog een ander pijnpunt van CSV zijn de quotes. Omdat het een tekstformaat is, moet je erg opletten bij het gebruik van bijvoorbeeld een line break in de data. Een line break (CRLF) is immers het scheidingsteken voor verschillende records. Wat nou als je één veld hebt waarin het complete adres van een bedrijf staat, inclusief line breaks? Hetzelfde probleem geldt natuurlijk voor komma's, die ook een speciale betekenis hebben. Daarom kun je, zoals in de RFC ook vermeld staat, quotes ("") gebruiken om data te markeren **waarin** line breaks worden gebruikt.

## Literatuur

Bestudeer het hoofdstuk "Manipulating files", inclusief het deel "Writing basic scripts" uit het boek *UNIX Visual Quickstart Guide* van Ray & Ray. Een deel is herhaling van de Software Carpentry-module, maar dit kan ook nuttig zijn als naslag.

## Vragen

Let op: als je testbestanden maakt, doe dat dan niet in Windows met Notepad of Atom. Gebruik in plaats daarvan `nano` (zoals uitgelegd in de Software Carpentry workshop). Dan zijn de line endings correct voor gebruik van `grep`.

1.  Geef een commando om alle lowercase letters in een bestand om te zetten naar uppercase.

1.  Wat is een *key field* voor het commando `sort`? Gebruik eventueel `man sort` om het uit te zoeken.

1.  Schrijf een geheim bericht in een bestand genaamd `brief.txt`. Geef een commando om alle letters in het bestand met 13 posities op te schuiven (dus `a` wordt `n`, `b` wordt `o` en `n` wordt `a`).

1.  Sorteer het volgende bestand (`desserts`) op type dessert (dus `pie`, `cake` enzovoort):

        blueberry pie
        chocolate cake
        apple strudel
        chocolate moose
        pumpkin pie
        molasses cookies
        chocolate fudge
        rhubarb pie
        strawberry tart
        cherry cobbler
        peach pie
        pound cake

    Welk commando moet je hiervoor geven?

1.  Bij een ander vak geven we [deze opdracht](https://pyprog.proglab.nl/opdrachten/week5/eca2csv) voor het schrijven van een programma om een databestand om te zetten in een beter formaat. Die cursus is in Python maar je kunt deze opdracht véél korter in UNIX doen. Geef een commando (met pipes) om deze datafile om te zetten naar het in de opdracht beschreven formaat. Het originele bestand kun je daar downloaden. (Opschonen van missende waarden is niet verplicht maar zou kunnen met `awk`).


1.  De lijst studenten van Programmeren 1 heeft wat problemen. We hebben deze in Excel opgeslagen als CSV en we kregen meteen deze melding:

    ![Possible Data Loss Some. features might be lost if you save this workbook in the comma-delimited (.csv) format. To preserve these features, save it in an Excel file format.](excel.png)

    Hadden we maar geluisterd... want we hebben de originele .xlsx weggegooid en nu zitten we met een [nogal onhandig te verwerken bestand](students_50621PRP6Y.csv). Je **moet** het downloaden via dit commando om de originele versie te krijgen:

        curl -OL https://raw.githubusercontent.com/minprog/datarepresentaties/2022/onderwerpen/4%20Text/csv/students_50621PRP6Y.csv

     Het volgende is mis:

    - Line endings zijn Mac OS 7-style `\r`, wat niet goed werkt met UNIX-tools
    - De laatste kolom is een opsomming van studies met komma ertussen, maar er staan geen quotes om heen
    - De kolommen zijn gescheiden met een puntkomma in plaats van een komma

    Geef de commando's, liefst een one-liner, om het bestand te corrigeren voor verdere verwerking als CSV.

1.  Geef een awk-script dat "Hello, World" naar het scherm print.

1.  Geef een awk-script dat van elke regel van de file `passwd` de username print, en of de gebruiker speciale privileges heeft. Dat laatste is alleen het geval als de gebruiker een niet-negatief ID kleiner dan 10 heeft ([download `passwd.txt` hier](passwd.txt)). Dat moet er zo uitzien:

        root    privileged
        daemon  privileged
        nobody  not privileged
        joedoe  not privileged

1.  Geef een awk-script dat alle gebruikers op dezelfde manier print, maar in dit geval moeten de gebruikers `root` en `daemon` worden overgeslagen omdat deze op elk systeem bestaan. Alleen de overige gebruikers worden dus geprint, op dezelfde manier als bij de vorige vraag.






## Inleveren

Lever hieronder een PDF in met je antwoorden. Gebruik géén titelpagina. Vermeld je naam en studentnummer, en de naam van de opdracht. Vermeld ook de vraag boven elk antwoord---dit mag een samengevatte versie van de vraag zijn. Als je informatie van buiten de aangeleverde tekst gebruikt moet je een bronvermelding doen; je mag gewoon de site/titel noemen in de tekst.

## Nakijken

De antwoorden worden kritisch nagekeken op zorgvuldige beantwoording. Dat betekent dat de antwoorden gebaseerd moeten zijn op de lesstof, dat wat er staat goed is en logisch onderbouwd en dat er geen onware of irrelevante beweringen of informatie bij de antwoorden staan. Aan de andere kant: een klein foutje is geen probleem.

