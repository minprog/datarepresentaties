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

## Literatuur

Bestudeer het hoofdstuk "Manipulating files", inclusief het deel "Writing basic scripts" uit het boek *UNIX Visual Quickstart Guide* van Ray & Ray. Een deel is herhaling van de Software Carpentry-module, maar dit kan ook nuttig zijn als naslag.

## Vragen

Let op: als je testbestanden maakt, doe dat dan niet in Windows met Notepad of Atom. Gebruik in plaats daarvan `nano` (zoals uitgelegd in de Software Carpentry workshop). Dan zijn de line endings correct voor gebruik van `grep`.

1.  Geef een commando om alle lowercase letters in een bestand om te zetten naar uppercase.

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

1.  Download [deze datafile](climate.txt) met daarin temperatuurwaarden van het KNMI in de Bilt, vanaf 1 januari 1901. De temperatuurwaarden zijn vermenigvuldigd met 10 zodat er geen komma of punt gebruikt hoeft te worden (`-24` is dus eigenlijk -2,4 graden).

    Ontwikkel een one-liner van UNIX-commando's die `climate.txt` neemt en daar de volgende operaties op uitvoert. Het resultaat moet worden opgeslagen in de file `climate-clean.txt`.

    1. Verwijderen van de header-regels. Alles tot de regel `DATE;TX` moet verwijderd worden. Je mag hiervoor tellen hoeveel regels het zijn en dit aantal hardcoden in je opdracht, of je detecteert op een of andere manier de blanco regel of de `DATE;TX`-regel.

    2. Verwijderen van de gegevens voor 2020. De data van 2020 zijn incompleet, lopen slechts tot maart. Om correcte gemiddelden voor een jaar uit te rekenen wil je geen incomplete data gebruiken. Je mag hier geen kennis van aantal regels gebruiken.

    3. Omzetten van puntkomma (`;`) naar komma (`,`). Zo is het een valide CSV-bestand, gescheiden door komma's.

    Geef in je uitwerking de oneliner.

1.  Geef een awk-script dat van elke regel van de file `passwd` de username print, en of de gebruiker speciale privileges heeft. Dat laatste is alleen het geval als de gebruiker een niet-negatief ID kleiner dan 10 heeft ([download `passwd.txt` hier](passwd.txt)). Het uiteindelijke resultaat moet er zo uitzien:

        root    privileged
        daemon  privileged
        uucp    privileged
        nobody  not privileged
        joedoe  not privileged

    Je mag voor deze vraag alleen `awk` gebruiken. Om deze vraag te beantwoorden moet je even flink in `awk` duiken en specifiek hoe je bepaalde waarden kunt filteren en voorwaarden kunt gebruiken. Dit is opzoeken en informatie combineren van internet, waarschijnlijk. Zorg dat je je uiteindelijke antwoord zodanig begrijpt dat je een variant van de vraag relatief makkelijk kunt beantwoorden.

1.  Geef een awk-script dat alle gebruikers op dezelfde manier print als hierboven, maar in dit geval moeten de gebruikers `root` en `daemon` worden *overgeslagen* omdat deze op elk systeem bestaan (zorg dat je filtert op deze namen en niet op een andere eigenschap zoals ID of status). Je print uiteindelijk dus dezelfde resultaten als hierboven, behalve `root` en `deamon`.

## Inleveren

Lever een PDF in met je antwoorden. Gebruik géén titelpagina. Vermeld je naam en studentnummer, en de naam van de opdracht. Vermeld ook de vraag boven elk antwoord---dit mag een samengevatte versie van de vraag zijn. Als je informatie van buiten de aangeleverde tekst gebruikt moet je een bronvermelding doen; je mag gewoon de site/titel noemen in de tekst.
