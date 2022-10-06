# CSV-formaat

> Bestudeer de stof en beantwoord de vragen hieronder. Je antwoorden worden beoordeeld op inzet en correctheid (1 punt voor de hele opdracht).

CSV is de simpelste manier om data te organiseren in een tekstbestand. Als de data een **tabel** is, dus als deze bestaat uit rijen en kolommen, dan kan CSV gebruikt worden om de data te organiseren.

De precieze definitie van het **Comma Separated Values** CSV-formaat is te vinden in een RFC-document. Zo'n RFC-document is een manier om een breed gebruikte werkwijze of bestandsformaat vast te leggen.

<https://datatracker.ietf.org/doc/html/rfc4180>

Let even op de terminologie. Een rij wordt ook wel een **record** genoemd. Elk record bevat alle gegevens van één ding. Een kolom wordt ook wel een **field** genoemd. Elk field is één soort gegeven, bijvoorbeeld een naam of een telefoonnummer.

Let op dat er ook nog andere formaten zijn zoals "tab separated values", die op een andere manier worden opgemaakt. Het idee is hetzelfde, maar je moet er rekening mee houden dat je zelf moet controleren of je commando's nog kloppen.

🌵 **Oefening.** Hieronder vind je de tekst van een CSV-bestand. Gebruik het `sort`-commando om het te sorteren op kamernummer. Standaard sorteert het commando alle regels op alfabet. Gebruik `man sort` om te achterhalen hoe je moet sorteren met velden (fields) en hoe je zorgt dat de komma wordt gebruikt om de twee velden te onderscheiden.

    Stegeman,L0.11
    van Assema,L0.09
    Vrielink,L0.10

Welk commando heb je uiteindelijk gebruikt? Leg uit hoe alle opties werken om het juiste resultaat te krijgen.

<textarea name="form[q0A]" rows="4" required></textarea>

## Encodings

Ook CSV-bestanden kunnen in verschillende encodings worden opgeslagen, dus niet alleen ASCII (zoals in de RFC staat) maar bijvoorbeeld ook UTF-8. Net als bij andere teksten is het niet altijd vooraf duidelijk welke encoding wordt gebruikt. Daarom kun je bij het inlezen vaak aangeven welke encoding het moet zijn. Zie bijvoorbeeld [deze pagina met instructies over het importeren van UTF-8 CSV-bestanden in Excel](https://www.nextofwindows.com/how-to-display-csv-files-with-unicode-utf-8-encoding-in-excel). Dit is ook relevant als je geautomatiseerd data gaat verwerken; je moet dan zorgen dat je meerdere formaten aankunt, of dat alle data gegarandeerd in hetzelfde formaat wordt aangeleverd.

## Quotes

Nog een ander pijnpunt van CSV zijn de quotes. Omdat het een tekstformaat is, moet je erg opletten bij het gebruik van bijvoorbeeld een line break in de data. Een line break (CRLF) is immers het scheidingsteken voor verschillende records. Wat nou als je één veld hebt waarin het complete adres van een bedrijf staat, inclusief line breaks? Hetzelfde probleem geldt natuurlijk voor komma's, die ook een speciale betekenis hebben. Daarom kun je, zoals in de RFC ook vermeld staat, quotes ("") gebruiken om data te markeren **waarin** line breaks worden gebruikt.

Het probleem is dat Excel, maar ook veel POSIX-tools, geen rekening houden met de quotes. Je moet dus dubbel opletten als je commando's gebruikt om CSV's te filteren en op een andere manier te bewerken. De tool `csvquote` kan hier goed bij helpen.

<https://github.com/dbro/csvquote>

## 🌵 Opdracht

1.  De lijst studenten van Programmeren 1 heeft wat problemen. We hebben deze in Excel opgeslagen als CSV en we kregen meteen deze melding:

    ![Possible Data Loss Some. features might be lost if you save this workbook in the comma-delimited (.csv) format. To preserve these features, save it in an Excel file format.](excel.png)

    Hadden we maar geluisterd... want we hebben de originele .xlsx weggegooid en nu zitten we met een [nogal onhandig te verwerken bestand](students_50621PRP6Y.csv). Je moet het downloaden via dit commando om de originele versie te krijgen:

        curl -OL https://raw.githubusercontent.com/minprog/datarepresentaties/2022/onderwerpen/5%20Tools/csv/students_50621PRP6Y.csv

     Het volgende is mis:

    - Line endings zijn Mac OS 7-style `\r`, wat niet goed werkt met UNIX-tools
    - De laatste kolom is een opsomming van studies met komma ertussen, maar er staan geen quotes om heen
    - De kolommen zijn gescheiden met een puntkomma in plaats van een komma

    Geef de commando's, liefst een one-liner, om het bestand te corrigeren voor verdere verwerking als CSV.

    <textarea name="form[q1]" rows="8" required></textarea>

1.  Geef een awk-script dat "Hello, World" naar het scherm print.

    <textarea name="form[e1]" rows="8" required></textarea>

1.  Geef een awk-script dat van elke regel van de file `passwd` de username print, en of de gebruiker speciale privileges heeft. Dat laatste is alleen het geval als de gebruiker een niet-negatief ID kleiner dan 10 heeft ([download `passwd.txt` hier](passwd.txt)). Dat moet er zo uitzien:

        root    privileged
        daemon  privileged
        nobody  not privileged
        joedoe  not privileged

    <textarea name="form[e2]" rows="8" required></textarea>

1.  Geeft een awk-script dat alle gebruikers op dezelfde manier print, maar in dit geval moeten de gebruikers `root` en `daemon` worden overgeslagen omdat op elk systeem bestaan. Alleen de overige gebruikers worden dus geprint, op dezelfde manier als bij de vorige vraag.

    <textarea name="form[e3]" rows="8" required></textarea>

