# Tekstcodering

1. Bestudeer onderstaande uitleg over tekstcodering,
2. hou goed bij wat je opvalt en wat je leert,
3. en beantwoord de vragen die in de tekst staan.

## Plain text

Bestanden met "plain text" zijn eigenlijk niets bijzonders. Zoals je eerder hebt gezien wordt ook tekst uiteindelijk in binair formaat opgeslagen, wat betekent dat zo'n tekst in het geheugen of op een harddisk wordt weggeschreven met nullen en enen. In die zin is het niets anders dan een formaat zoals MP3 om muziek op te slaan of docx om tekst en lay-out op te slaan.

Platte tekst heeft echter een aparte plaats in de computerwereld vanwege het enorme aantal toepassingen dat eenvoudige tekst gebruikt en omdat platte-tekstbestanden (in de meeste gevallen) gemakkelijk door mensen kunnen worden gelezen, ook als het programma waarmee het is gemaakt, even niet beschikbaar is. Platte tekst kan dus worden weergegeven met vrijwel elke computer zonder speciale programma's, zoals je die wel nodig zou hebben voor bijvoorbeeld het weergeven van een 3D-model van een menselijk orgaan.

Ook platte tekst levert toch wat problemen op. Het zou erg handig zijn geweest als elk woord in welke taal dan ook kon worden uitgedrukt met behulp van de 256 verschillende karakters van ASCII. En ja, er is wel [geprobeerd](https://en.wikipedia.org/wiki/Transliteration_of_Chinese) om andere talen "compatibel" te maken met het Engels. Maar realistisch gezien is ASCII niet flexibel genoeg, en heeft gewoon niet genoeg verschillende tekens. Daarom zijn er **verschillende coderingen om tekst te beschrijven met nullen en enen**.

## Unicode

Bij het onderdeel over binaire representatie heb je al gelezen over Unicode. Unicode is een modernere uitvinding en daarbij veel ambitieuzer dan ASCII: het heeft tot doel zoveel mogelijk menselijke schriften weer te geven (momenteel 159), evenals verschillende soorten symbolen. Er zijn zo'n 100.000 tekens gedefinieerd in Unicode, en het aantal neemt elk jaar toe.

Het mogelijk maken van zoveel verschillende tekens wordt in feite gedaan door het aantal **beschikbare bits te vergroten** waarmee één teken wordt gerepresenteerd (elk "teken" of character wordt in Unicode een "code point" genoemd). In het boek wordt zelfs gezegd dat Unicode altijd 16 bits per codepunt gebruikt. Een tijdlang is Unicode inderdaad op die manier gebruikt: simpelweg 2 bytes per letter. Dat geeft een heleboel extra ruimte.

Tegelijk is het niet zo efficiënt als je voor alle letters 2 bytes gaat gebruiken. Elke file in Unicode wordt dan 2x zo groot als in ASCII (als je bijvoorbeeld Engels schrijft). Daarom wordt Unicode-tekst tegenwoordig meestal opgeslagen met **UTF-8**-codering. In deze codering kunnen code points **1 of meer** bytes innemen, in plaats van altijd 2. Hoe werkt dat? Kijk eens naar het volgende:

![embed](https://www.youtube.com/embed/MijmeoH9LT4)

Dit is relevant als je geautomatiseerd data gaat verwerken; je moet dan zorgen dat je meerdere formaten aankunt, of dat alle data gegarandeerd in hetzelfde formaat wordt aangeleverd.

## Verwarring tussen ASCII en Unicode

Het mooie is dat de eerste 128 tekens van Unicode precies zo zijn gecodeerd als in ASCII. Het allereerste bit in de binaire representatie is in die gevallen altijd **0** (kijk maar naar de ASCII-tabel). De resterende 7 bits worden gebruikt om het specifieke teken te coderen. Tekens die beginnen met een **1** worden wél anders geïnterpreteerd in Unicode UTF-8 dan in ASCII. Je mag er daarom bij UTF-8 niet meer vanuit gaan dat byte die begint met een 1 een teken is dat je in de ASCII-tabel kunt opzoeken.

Dat is allemaal niet zo'n probleem, als je maar weet of een bestand ASCII of Unicode UTF-8 is.

En dat is waar het nu net mis gaat. Er staat namelijk bovenaan een tekstbestand géén indicatie staat of het Unicode is of ASCII. Een tekstbestand bevat immers de tekst zelf en niets anders.

Aan de bytes kun je het ook niet echt zie. Als je ze inspecteert zie je gewoon een heleboel bytes waarvan de meeste met een 0 beginnen (als je Engelse of Nederlandse tekst schrijft) maar je ziet waarschijnlijk ook bytes die met een 1 beginnen. Met jouw kennis van taal kun je soms wel zien of ASCII hier de juiste tekst geeft, maar een computer kan dit niet zomaar "zien". Daarom kan het gebeuren dat je een tekst opent en sommige tekens er vreemd uitzien.

Conclusie: dit betekent dat elke ASCII-tekst (maar dus niet elke tekst in *extended ASCII*) geldige UTF-8 is. Met andere woorden, veel bestanden die oorspronkelijk opgeslagen zijn in ASCII kunnen worden gelezen alsof het UTF-8 is.

Andersom is lastiger: als je een UTF-8 bestand opent in een teksteditor die dit niet verwacht, of helemaal niet aankan, dan kan het zijn dat bepaalde letters anders zijn dan verwacht. Ook programma's in oude programmeertalen zoals Python versie 2 kunnen dit probleem hebben.

Encodings voor tekst zijn dus een beetje gedoe, omdat in de tekst niet staat welke encoding is gebruikt. In de praktijk speelt het probleem steeds minder vaak, maar duikt wel plotseling weer op als je bijvoorbeeld met een wat oudere dataset aan de slag gaat.

## Regeleindes

ASCII en Unicode bevatten naast letters ook een aantal veelgebruikte control-codes, ook wel "unprintable characters" genoemd. Enkele van die tekens representeren het "einde" van iets, en de belangrijkste zijn de twee tekens die het **einde van een regel** markeren. Hier staan ze in een tabel met hun code-nummer:

| Code | Hex | Meaning         | Acronym | Escape |
| ---- | --- | --------------- | ------- | ------ |
| 10   | 0a  | line feed       | LF      | \n     |
| 13   | 0d  | carriage return | CR      | \r     |

Historisch gezien hebben de twee tekens een totaal verschillend doel: line feed gaat naar de **volgende** regel, en carriage return gaat naar het **begin** van de (huidige) regel. Dit verschil maakt uit bij zoiets als een "[matrix printer](https://en.wikipedia.org/wiki/Dot_matrix_printing#/media/File:Printer_dot_matrix_EPSON_VP-500.jpg)" maar niet in moderne toepassingen.

In tekstbestanden die we op het scherm tonen, of bewerken, is het nog steeds nodig om aan te geven als een regel "eindigt", want hoe hebben we anders een paragraaf? Ook hiervoor worden CR en LF gebruikt, maar op verschillende systemen gaat het wel om verschillende combinaties van beide. Dit is wel iets makkelijker te detecteren dan het gebruik van UTF-8, maar toch is het erg onhandig.

| Characters | Operating System |
| ---------- | ---------------- |
| CR         | Old Mac OS files |
| LF         | Most UNIX files + Mac OS X |
| CRLF       | Windows files    |

Zoals je ziet wordt op oude Mac-systemen CR gebruikt, en op moderne UNIX-gebaseerde systemen LF. Windows doet het wéér anders (maar wel al heel lang op dezelfde manier), namelijk door beide tekens achter elkaar te gebruiken! Elk regeleinde in een tekstbestand gemaakt onder Windows kost dus 16 bytes.

Je kunt al deze combinaties tegenkomen als je een tekstbestand hebt met onbekende herkomst. Sommige programma's achterhalen automatisch wat de bedoeling is (ofwel, elke combinatie van CR/LF beschouwen ze als regeleinde). Andere programma's houden star vast aan hun eigen conventie. Als jij een tekstbestand inlaadt in een zelfgeschreven programma moet je hier dus wel op letten.

**Oefening.** Maak een bestand in de Terminal door de uitvoer van `cat` te redirecten naar een bestand genaamd `bla`. Je tikt een aantal regels in, steeds gevolgd door ENTER. Om te eindigen tik je de combinatie CTRL-D in op een lege regel. CTRL-betekent "end of input", waarmee je aangeeft dat er niets meer volgt en het programma de verwerking mag beëindigen. Het zou er zo uit moeten zien:

    % cat > bla
    hoe
    dan
    ^D

Stel dat je op macOS werkt, en via `xxd` de bytes van het bestand bekijkt, dan ziet het er zo uit:

    % xxd -g1 bla 
    00000000: 68 6f 65 0a 64 61 6e 0a                          hoe.dan.

Met `xxd` krijg je toegang tot de hexadecimale representatie van de bytes in het bestand. Het getal 68 (hex) is het teken `h` in ASCII. Vaak zie je ook hexadecimale versies in de ASCII-tabel staan, dus dan kun je het makkelijk opzoeken. Hierboven zie je voor CR en LF ook de hexadecimale representatie.

Je ziet dat direct na elk woord `hoe` en `dan` alléén een `0a` staat. Dit is `10` in decimale representatie en dus een LF. Dit is wat we verwachten van Mac OS (en Linux). Als je Windows hebt met WSL, probeer dan bovenstaand recept ook in de WSL Terminal. En maak eens een bestand in Windows Notepad, en bekijk daar de inhoud van met `xxd`.

## Witruimte (white space)

In de character sets van ASCII en Unicode komen ook tekens voor dit een vorm van witruimte voorstellen. De bekendste is de spatie (space) die in ASCII het getal 32 heeft gekregen. Hiermee worden meestal woorden onderscheiden in een tekst.

Een ander teken dat witruimte voorstelt is "tab", ofwel ASCII 9. Dit teken wordt historisch gebruikt om verschillende onderdelen van een dataregel te onderscheiden. Op het beeldscherm wordt een tab op een speciale manier weergegeven, met 1 of meer spaties.

Unicode bevat nog meer soorten spaties die interessant zijn om meer controle te hebben over typografie---relevant als je bijvoorbeeld een webpagina of een Word-document aan het maken bent. Zo is er bijvoorbeeld de ["thin space"](https://www.compart.com/en/unicode/U+2009) die iets minder ruimte inneemt en in bepaalde situaties gebruikt zou moeten worden.

Voor dataverwerking is de relevante vraag: wat wordt gezien als witruimte en wat betekenen de verschillende soorten? Hoe je witruimte interpreteert hangt van het doel af. Stel dat je een bestand hebt met twee regels:

    These are two
    words.

Als je "zinnen" wil onderscheiden in dit bestand dan doet de CR/LF aan het eind van de regel niet ter zake. De zin eindigt bij een punt. Maar "two" en "words" zijn wel twee *verschillende* woorden. Toch staat géén spatie tussen, maar alleen een CR/LF. Een CR/LF kunnen we dus als relevante witruimte zien als we individuele woorden in een tekst willen herkennen. Bijvoorbeeld als je simpelweg het aantal woorden in een tekst wil tellen.

## Conclusie

Wat we maar willen zeggen: alles op de computer is kunstmatig. Iemand heeft een beslissing genomen (waarschijnlijk een heel comité) en vanaf dat moment wordt op een bepaald systeem, of in een bepaald deel van de wereld die beslissing gevolgd (dit heet ook wel een **conventie**). Daarnaast kan in bepaalde toepassingen een bepaalde conventie gevolgd worden. Als programmeur moet je altijd in je achterhoofd houden dat files verschillende herkomsten kunnen hebben en op een andere manier in elkaar zitten. Of je moet juist files schrijven die voor een bepaalde doelgroep zijn.

## Opdracht

De lijst studenten van Programmeren 1 heeft wat problemen. We hebben deze in Excel opgeslagen als CSV en we kregen meteen deze melding:

![Possible Data Loss. Some features might be lost if you save this workbook in the comma-delimited (.csv) format. To preserve these features, save it in an Excel file format.](excel.png)

Hadden we maar geluisterd... want we hebben de originele .xlsx weggegooid en nu zitten we met een [nogal onhandig te verwerken bestand](students_50621PRP6Y.csv). Je **moet** het downloaden via dit commando om de originele versie te krijgen:

    curl -OL https://raw.githubusercontent.com/minprog/datarepresentaties/2022/onderwerpen/4%20Text/csv/students_50621PRP6Y.csv

Het volgende is mis:

- Line endings zijn Mac OS 7-style `\r`, wat niet goed werkt met UNIX-tools
- De laatste kolom is een opsomming van studies met komma ertussen, maar er staan geen quotes om heen
- De kolommen zijn gescheiden met een puntkomma in plaats van een komma

Geef de commando's, liefst een one-liner, om het bestand te corrigeren voor verdere verwerking als CSV. Je kunt dit doen met hulp van de UNIX-tools die je eerder hebt leren kennen.

## Inleveren

Lever hieronder een PDF in met je uitwerkingen. Gebruik géén titelpagina. Vermeld je naam en studentnummer, en de naam van de opdracht. Vermeld ook de vraag boven elk antwoord---dit mag een samengevatte versie van de vraag zijn. Als je informatie van buiten de aangeleverde tekst gebruikt moet je een bronvermelding doen; je mag gewoon de site/titel noemen in de tekst.

## Nakijken

De antwoorden worden kritisch nagekeken op zorgvuldige beantwoording. Dat betekent dat de antwoorden gebaseerd moeten zijn op de lesstof, dat wat er staat goed is en logisch onderbouwd en dat er geen onware of irrelevante beweringen of informatie bij de antwoorden staan. Aan de andere kant: een klein foutje is geen probleem.
