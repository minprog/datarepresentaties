# Pipelines in UNIX

Deze pagina bevat oefenmaterialen om je voor te bereiden voor het tentamenonderdeel "UNIX-pipelines".

## Over het CSV-formaat

CSV is de simpelste manier om data te organiseren in een tekstbestand. Als de data een **tabel** is, dus als deze bestaat uit rijen en kolommen, dan kan CSV gebruikt worden om de data te organiseren.

De precieze definitie van het **Comma Separated Values** CSV-formaat is te vinden in een RFC-document. Zo'n RFC-document is een manier om een breed gebruikte werkwijze of bestandsformaat vast te leggen.

<https://datatracker.ietf.org/doc/html/rfc4180>

Let even op de terminologie. Een rij wordt ook wel een **record** genoemd. Elk record bevat alle gegevens van één ding. Een kolom wordt ook wel een **field** genoemd. Elk field is één soort gegeven, bijvoorbeeld een naam of een telefoonnummer.

Let op dat er ook nog andere formaten zijn zoals "tab separated values", die op een andere manier worden opgemaakt. Het idee is hetzelfde, maar je moet er rekening mee houden dat je zelf moet controleren of je commando's nog kloppen.

**Vraag 0.** Hieronder vind je de tekst van een CSV-bestand. Gebruik het `sort`-commando om het te sorteren op kamernummer. Standaard sorteert het commando alle regels op alfabet. Gebruik `man sort` om te achterhalen hoe je moet sorteren met velden (fields) en hoe je zorgt dat de komma wordt gebruikt om de twee velden te onderscheiden.

    Stegeman,L0.11
    van Assema,L0.09
    Vrielink,L0.10

Welk commando heb je uiteindelijk gebruikt? Leg uit hoe alle opties werken om het juiste resultaat te krijgen.

## Workshop

Gebruik de website van [Software carpentry](https://swcarpentry.github.io/shell-novice/) om de workshop te doen.

2.  Vergeet niet om op de Setup-pagina van de workshop de **zip-file** te downloaden waarin alle bestanden staan om mee te oefenen, als je dit nog niet gedaan had.

3.  Doe alle oefeningen van **hoofdstukken 4, 5 en 6**. Het doel is om goed voorbereid te zijn voor de komende weken. Je doet dit door goed te oefenen en commando's **over te tikken** en de resultaten te bestuderen. Als je mazzel hebt maak je ook nog een paar tikfouten waardoor je moet achterhalen wat er fout ging: dan leer je het meest.

4.  In sommige gevallen matcht de omgeving niet met de omgeving die jij op je computer hebt. Zorg dat je uitzoekt hoe je dan moet handelen en betrek de assistenten hierbij. Je zou elk commando in de workshop moeten kunnen uitproberen.
