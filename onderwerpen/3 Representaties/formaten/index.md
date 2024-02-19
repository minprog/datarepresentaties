# Bestandsformaten

1. Bestudeer onderstaande uitleg over gebruik van `xxd`
2. hou goed bij wat je opvalt en wat je leert,
3. en doe dan de opdracht.

## xxd

Bestanden bevatten data die met hulp van programma's zijn opgeslagen. Als je een tekst-editor gebruikt kun je heel direct ASCII-tekens intikken en dan opslaan. Elk ASCII-teken dat je hebt ingetikt is een byte in dat bestand. Maar er zijn nog veel meer bestandsformaten.

Met de tool `xxd` kun je de inhoud van bestanden bekijken. Als er tekst in staat (in ASCII) dan wordt deze getoond, maar daarnaast staan ook de hexadecimale codes, waardoor het mogelijk wordt om te begrijpen hoe een bestand in elkaar zit dat geen tekst bevat.

Hieronder roepen we `xxd` aan met het bestand `course.yml`. YAML is een tekstformaat, maar het wordt gebruikt voor het opslaan van *gestructureerde* data. De bestanden bestaan grotendeels uit leesbare tekens uit de ASCII-tabel. Daarom zie je rechts ook bijna alleen maar leesbare tekst.

    % xxd -g 1 course.yml
    00000000: 6c 6f 6e 67 5f 6e 61 6d 65 3a 20 44 61 74 61 72  long_name: Datar
    00000010: 65 70 72 65 73 65 6e 74 61 74 69 65 73 0a 73 68  epresentaties.sh
    00000020: 6f 72 74 5f 6e 61 6d 65 3a 20 44 61 74 61 0a 6c  ort_name: Data.l
    00000030: 61 6e 67 75 61 67 65 3a 20 6e 6c 0a              anguage: nl.

Elk ASCII-teken wordt weergegeven door middel van een hexadecimaal getal dat bestaat uit 2 tekens.
Je ziet dat het getal `0a` drie keer voorkomt. Welk teken uit de ASCII-tabel is dit? Waarom wordt het weergegeven als een `.` in de rechterkolom? Bespreek je ideeën met medestudenten en de assistenten, zodat je goed begrijpt wat `xxd` jou laat zien (voordat je verder gaat!).

De optie `-g 1` hebben we hier gebruikt om de hexadecimale getallen apart neer te zetten. Als je deze optie weglaat worden de hexadecimale getallen gegroepeerd per 2 tekens. Dat ziet er dus bijna hetzelfde uit:

    % xxd course.yml           
    00000000: 6c6f 6e67 5f6e 616d 653a 2044 6174 6172  long_name: Datar
    00000010: 6570 7265 7365 6e74 6174 6965 730a 7368  epresentaties.sh
    00000020: 6f72 745f 6e61 6d65 3a20 4461 7461 0a6c  ort_name: Data.l
    00000030: 616e 6775 6167 653a 206e 6c0a            anguage: nl.

## Binaire data

Nu bekijken we met hulp van de flag `-l` de eerste 128 bytes van een MP4-bestand waarin video is opgeslagen:

    % xxd -l 128 outro.mp4
    00000000: 0000 001c 6674 7970 6d70 3432 0000 0001  ....ftypmp42....
    00000010: 6973 6f6d 6d70 3431 6d70 3432 0000 0001  isommp41mp42....
    00000020: 6d64 6174 0000 0000 0013 031a 00f4 5828  mdat..........X(
    00000030: 5046 1405 8503 62c0 5870 1652 0984 8a55  PF....b.Xp.R...U
    00000040: 71be b99c 6e26 6b2a 4d62 28a4 a948 802a  q...n&k*Mb(..H.*
    00000050: 20f7 cae6 e18c f4bf 9f63 f8e9 7b9d 76df   ........c..{.v.
    00000060: 47fd 97fe 68f8 bbbe 7d5e aeaf f75f 5b2a  G...h...}^..._[*
    00000070: 9240 8dd7 4771 6b40 ffc0 ede5 eecb c57d  .@..Gqk@.......}

Voor het opslaan van video worden allerlei formaten gebruikt waarmee beeld en geluid op een efficiënte manier binair kunnen worden gecodeerd. ASCII speelt daar dus geen rol meer, omdat de waarden van bijvoorbeeld kleuren direct binair worden opgeslagen. Je ziet hierboven dan ook dat het grootste deel van de data geen geldige ASCII-tekens bevat: `xxd` toont veel puntjes en schijnbaar willekeurige letters. Dat is een indicatie dat het niet om een tekstbestand gaat.

Toch staan er wel degelijk een paar reeksen letters in de bovenstaande data, waardoor we vermoeden dat die kleine stukjes daadwerkelijk bedoeld zijn als een stukje ASCII. Specifiek zien we twee keer de string `mp4` staan, wat niet geheel toevallig ook de naam van het bestandsformaat is. Dat is dus niet de video zelf maar kennelijk een beschrijving van het bestand. Hiervoor is ASCII gebruikt.

## Magic bytes

Die letters `mp4` die we in het bestand hebben gevonden zijn wel ergens voor bedoeld. Als je naar een rijtje bestanden kijkt kun je in heel veel gevallen via de bestands-**extensie** achterhalen wat voor bestand het betreft. Zo zijn bestanden die eindigen op `.mp4` bijna altijd audiobestanden in het MP4-formaat. En bestanden die eindigen op `.doc` zijn bijna altijd bestanden die gemaakt zijn in een oude versie van Microsoft Word (nieuwere versies gebruiken `.docx`). Daarom kun je in Windows en macOS ook dubbelklikken om een bestand direct in het juiste programma te openen.

Maar de inhoud van het bestand zelf kan ook een clou geven over het formaat. Je kunt makkelijk zelf inspecteren of een bestand een tekst-bestand is (dan zou je reeksen herkenbare tekst vinden en weinig anders, zoals hierboven in `course.yml`). Bij bestanden met een eigen indeling worden vaak **herkennigstekens** gebruikt om vast te leggen welk formaat het is, of welke versie van een formaat. Zo zijn bestanden gemaakt in Word 2.0 van een ander formaat dan die van Word 4.1. Toch maken ze beide bestanden die eindigen op de extensie `.doc`.

Een onderdeel van de herkenningstekens zijn de **magic bytes**. Dit zijn de tekens of getallen die helemaal aan het begin of eind van een bestand staan en een clou geven over het programma waarin het geopend kan worden. Heb je een 3D-model gemaakt in het programma Blender, dan wordt dit opgeslagen in een bestand met de extensie `.blend`. Maar het bestand begint ook *altijd* met de ASCII-tekens `BLEND`. Dat betekent overigens niet dat elk bestand dat begint met `BLEND` ook een Blender-bestand is. Je kunt immers een tekstbestand maken dat precies met dezelfde letters begint.

Zie [Wikipedia](https://en.wikipedia.org/wiki/List_of_file_signatures) voor een lijstje met voorbeelden van zulke magic bytes. De lijst zal niet compleet zijn, maar geeft een idee van enkele belangrijke formaten waarin magic bytes gebruikt worden.

## Zip-bestanden

Omdat opslagruimte steeds goedkoper is geworden, zie je dat steeds vaker tekstbestanden gebruikt om informatie te coderen die geen tekst is. Dit is helemaal niet zo efficiënt, maar in veel gevallen wel makkelijker programmeren. Ook zie je vaker dat bestanden bestaan uit een combinatie van plaatjes en teksten. De plaatjes worden dan in een efficiënt formaat zoals PNG opgeslagen, en de teksten gewoon als ASCII of Unicode. Het nadeel is dat je dan niet één bestand hebt maar meerdere.

Heel vaak wordt voor samengestelde bestanden het ZIP-formaat gebruikt. Het bestand is dan een ZIP-archief waarin meerdere bestanden zijn opgeslagen. Zo is het toch één enkel bestand dat je kunt gebruiken om alle informatie in op te slaan (en dat kun je dan bijvoorbeeld makkelijk naar iemand anders sturen). Deze bestanden zijn aan de extensie niet herkenbaar als zip-bestand! Zo kun je bijvoorbeeld met het programma OmniGraffle diagrammen tekenen. De gebruikte extensie is hier `.graffle`. Maar intern kunnen we herkennen dat het om een ZIP-bestand gaat:

    % xxd -l 128 minoren.graffle 
    00000000: 504b 0304 1400 0000 0800 6f98 7254 2108  PK........o.rT!.
    00000010: 6f65 8a39 0000 c0d4 0000 0a00 0000 6461  oe.9..........da
    00000020: 7461 2e70 6c69 7374 ed9d 0760 13e5 1ff7  ta.plist...`....
    00000030: 9f1b e9a2 8514 e862 9440 d9b4 257b 94d1  .......b.@..%{..
    00000040: bda0 7b53 0a25 4dae 6d20 4d4a 9296 0e0a  ..{S.%M.m MJ....
    00000050: 6d59 b245 f690 d1b2 41a6 2c91 8d88 88ec  mY.E....A.,.....
    00000060: a9a0 a0a2 8288 2822 080a efef 2e49 1b68  ......(".....I.h
    00000070: a2c8 2b7f 7d5f 9a34 cd73 77cf 3d77 f77c  ..+.}_.4.sw.=w.|

De tekens `PK` geven hier een indicatie dat het een ZIP-bestand is. Je kunt op de Wikipedia-pagina hierboven kijken om dit te dubbelchecken.

Wat je vervolgens kunt doen is het bestand **hernoemen** naar `minoren.zip` en dan uitpakken door te dubbelklikken. Als alternatief kun je het ook uitpakken via de command line:

    % unzip -d uitgepakt minoren.graffle 
    Archive:  minoren.graffle
      inflating: uitgepakt/data.plist          
      inflating: uitgepakt/preview.jpeg        

Dan zie je dat er twee bestanden in staan: een databestand (formaat is kennelijk `.plist`) en een preview-plaatje. Het programma OmniGraffle weet dat deze bestanden er in moeten staan en zorgt ervoor dat elk bestand dit formaat heeft.

## Opdracht

[Download een ZIP-bestand](files.zip) met daarin 10 andere bestanden (het wachtwoord is `secret`). Deze bestanden hebben geen duidelijke naam die weggeeft wat voor soort bestand het is. Is het een document, een audio-file? Je kunt natuurlijk de extensies aanpassen en het bestand proberen te openen in Word of in een audioplayer. Maar dat is hier niet de bedoeling! In dit geval gaat `xxd` ons helpen om te analyseren wat er in de bestanden staat.

Geef in jouw uitwerking per bestand aan:

- welk formaat het heeft;
- op basis waarvan je precies die conclusie kunt trekken;
- welke extensie het zou moeten hebben;
- met welk programma je het document uiteindelijk geopend hebt toen je wist wat voor formaat het had;
- geef ook een idee van de inhoud zodat we kunnen zien dat je het goed begrepen hebt (geen copy-paste van de inhoud, maar een beschrijving in jouw eigen woorden)

In principe moet je voor elk bestand kunnen achterhalen wat het is, maar soms is het even lastig.

## Beoordeling

Je krijgt gelijke deelpunten per bestand waarvan je achterhaalt wat het precies voor formaat is (zo gedetailleerd mogelijk) en wat er in staat. Belangrijker is dat je per bestand heel precies documenteert hoe het in elkaar zit, voor zover dat nodig is om uit te leggen welk formaat het betreft. Soms is het zo simpel als een paar magic bytes, soms moet je meer uitleggen. Als je stappen in je redenatie overslaat krijg je geen punt.

## Inleveren

Lever een PDF in met je antwoorden. Gebruik géén titelpagina. Vermeld je naam en studentnummer, en de naam van de opdracht. Vermeld ook de vraag boven elk antwoord---dit mag een samengevatte versie van de vraag zijn. Als je informatie van buiten de aangeleverde tekst gebruikt moet je een bronvermelding doen; je mag gewoon de site/titel noemen in de tekst.
