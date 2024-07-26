# Pipelines in UNIX

Deze pagina bevat oefenmaterialen om je voor te bereiden voor het tentamenonderdeel "UNIX-pipelines".

## Over het CSV-formaat

CSV is de simpelste manier om data te organiseren in een tekstbestand. Als de data een **tabel** is, dus als deze bestaat uit rijen en kolommen, dan kan CSV gebruikt worden om de data te organiseren.

De precieze definitie van het **Comma Separated Values** CSV-formaat is te vinden in een RFC-document. Zo'n RFC-document is een manier om een breed gebruikte werkwijze of bestandsformaat vast te leggen.

<https://datatracker.ietf.org/doc/html/rfc4180>

Let even op de terminologie. Een rij wordt ook wel een **record** genoemd. Elk record bevat alle gegevens van één ding. De gegevens zijn gescheiden door een **separator**, een komma. In principe heeft elke regel precies evenveel kolommen aan informatie, gescheiden door komma's. Een kolom wordt ook wel een **field** genoemd. Elk field is één soort gegeven, bijvoorbeeld een naam of een telefoonnummer.

Let op dat er ook nog andere formaten zijn zoals "tab separated values" (met tabs in plaats van komma's). Het idee is vaak hetzelfde, maar als je UNIX-tools gebruikt met andere soorten bestanden moet je vaak extra opties meegeven om de tool uit te leggen wat deze kan verwachten.

## Workshop

Gebruik de website van [Software carpentry](https://swcarpentry.github.io/shell-novice/) om de workshop te doen.

2.  Vergeet niet om op de Setup-pagina van de workshop de **zip-file** te downloaden waarin alle bestanden staan om mee te oefenen, als je dit nog niet gedaan had.

3.  Doe alle oefeningen van **hoofdstukken 4, 5 en 6**. Het doel is om goed voorbereid te zijn voor de komende weken. Je doet dit door goed te oefenen en commando's **over te tikken** en de resultaten te bestuderen. Als je mazzel hebt maak je ook nog een paar tikfouten waardoor je moet achterhalen wat er fout ging: dan leer je het meest.

4.  In sommige gevallen matcht de omgeving niet met de omgeving die jij op je computer hebt. Zorg dat je uitzoekt hoe je dan moet handelen en betrek de assistenten hierbij. Je zou elk commando in de workshop moeten kunnen uitproberen.
