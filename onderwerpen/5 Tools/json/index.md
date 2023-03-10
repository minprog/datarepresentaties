# JSON

1. Bestudeer onderstaande uitleg over JSON,
2. en de materialen die gelinkt zijn,
3. en hou goed bij wat je opvalt en wat je leert.

## Het JSON tekst-formaat

JSON is een formaat om hierarchische structuren uit te drukken in simpele tekst. Je kunt het in de praktijk gebruiken om data uit te wisselen. Sommige websites bieden dan ook de mogelijkheid om data op te vragen in JSON-formaat, vaak zodat je die data kunt gebruiken om een andere website mee te bouwen.

JSON is een soort tegenhanger van een ouder formaat, XML. XML biedt ongeveer de zelfde mogelijkheden maar de syntax (manier van schrijven) is veel ingewikkelder. In de praktijk kunnen de meeste toepassingen prima gebruik maken van alleen maar JSON.

## Hiërarchie

De basis van JSON is dat je twee soorten structuren hebt die weer andere structuren kunnen bevatten. Dit zijn *objecten* en *arrays*. Het feit dat structuren andere structuren bevatten maakt dat je hierarchiën kunt beschrijven in JSON.

Zo kun je een rijtje van objecten vatten in een array (denk aan een lijst van medewerkers). En je kunt een object "eigenschappen" meegeven waarin je weer andere waarden stopt (denk aan een persoon die een naam heeft en een huisnummer).

## Syntax

Dit alles wordt gevat in een zeer eenvoudige syntax. Er is een [formele specificatie](https://www.ecma-international.org/wp-content/uploads/ECMA-404_2nd_edition_december_2017.pdf) van deze JSON-syntax. De paragrafen 4 t/m 9 zijn de complete specificatie van de taal. Men gebruikt zogenaamde "railroad diagrams" om uit te leggen waar JSON aan moet voldoen. Zorg dat je [deze korte handleiding] van railroad diagrams doorneemt en dan heel precies begrijpt wat een **valide** JSON-document is.

Een opmerking die wordt gemaakt in de specificatie is dat JSON weliswaar een **syntax** definieert maar dat de bijbehorende **semantiek** (betekenis van de inhoud) niet vastligt. Elke gebruiker van JSON moet afspraken maken of vastleggen over welke data precies gecommuniceerd wordt en wat je er mee kunt. Als je verwacht dat er een lijst van medewerkers wordt verstuurd dan zal de JSON wel een array zijn met daarin objecten.

In feite geldt hetzelfde voor CSV: ook daar kun je niet aan de data ontlenen wat er bedoeld wordt.

## jq

Met de tool `jq` kun je data uit JSON-bestanden extraheren. Er is een speciale syntax voor het schrijven van kleine "queries" die aangeven welke data je wil hebben.

Bestudeer goed de volgende pagina: <https://www.baeldung.com/linux/jq-command-json>

## Movie data

Via [deze link](https://raw.githubusercontent.com/prust/wikipedia-movie-data/master/movies.json) kun je een bestand downloaden met alle filminformatie die iemand van Wikipedia heeft gehaald. Bestudeer de structuur.

## Opdrachten

1.  Geef een commando om alleen de gegevens van de eerste film uit het bestand te laten zien.

2.  Geef een commando om alleen de titel van de eerste film uit het bestand te laten zien.

3.  Geef een commando om de titels van alle films uit het bestand te laten zien.

4.  Geef een commando om de titels van alle films uit het bestand te laten zien, zonder aanhalingstekens (met hulp van `sed`).

## Inleveren

Lever hieronder een PDF in met je uitwerkingen. Gebruik géén titelpagina. Vermeld je naam en studentnummer, en de naam van de opdracht. Vermeld ook de vraag boven elk antwoord---dit mag een samengevatte versie van de vraag zijn.

## Nakijken

De antwoorden worden kritisch nagekeken op zorgvuldige beantwoording. Dat betekent dat de antwoorden gebaseerd moeten zijn op de lesstof, dat wat er staat goed is en logisch onderbouwd en dat er geen onware of irrelevante beweringen of informatie bij de antwoorden staan. Aan de andere kant: een klein foutje is geen probleem.

<!-- ## Links

- http://itsthisforthat.com/api.php?json
- https://ghibliapi.herokuapp.com/
- https://data.rijksmuseum.nl/object-metadata/api/
- https://data.mprog.nl/acquisition/scraping -->
