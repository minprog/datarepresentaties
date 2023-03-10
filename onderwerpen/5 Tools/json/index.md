# JSON

1. Bestudeer onderstaande uitleg over JSON,
2. en de materialen die gelinkt zijn,
3. en hou goed bij wat je opvalt en wat je leert.

## Het JSON tekst-formaat

JSON is een formaat om hierarchische structuren uit te drukken in simpele tekst. Je kunt het in de praktijk gebruiken om data uit te wisselen. Sommige websites bieden dan ook de mogelijkheid om data op te vragen in JSON-formaat, vaak zodat je die data kunt gebruiken om een andere website mee te bouwen.

JSON is een soort tegenhanger van een ouder formaat, XML. XML biedt ongeveer de zelfde mogelijkheden maar de syntax (manier van schrijven) is veel ingewikkelder. In de praktijk kunnen de meeste toepassingen prima gebruik maken van alleen maar JSON.

## Hiërarchie

De basis van JSON is dat je twee soorten structuren hebt die weer andere structuren kunnen bevatten. Dit zijn *objecten* en *arrays*. Het feit dat structuren andere structuren bevatten maakt dat je hierarchiën kunt beschrijven in JSON.

Zo kun je een rijtje van objecten vatten in een array (denk aan een lijst van medewerkers). En je kunt een object "eigenschappen" meegeven waarin je weer andere waarden stopt (denk aan een persoon die een naam heeft en een huisnummer). Die laatste lijkt wel op een dictionary in Python.

Hieronder een *array* met daarin twee *objects*. Elk object heeft daarin twee attributes, `name` en `address`. De waarde van `address` is ook weer een object, met daarin twee attributes, `street` en `number`.

Naast arrays en objects zijn er nog slechts twee soorten informatie in JSON (types), namelijk *numbers* en *strings*. In het voorbeeld hieronder zijn `name` en `street` allebei strings, en `number` is een... number.

    [
        {
            "name": "Ford Prefect",
            "address": {
                "street": "Science Park",
                "number": 900
            }
        },
        {
            "name": "Arthur Dent",
            "address": {
                "street": "Science Park",
                "number": 900
            }
        }
    ]

## Syntax

Dit alles wordt gevat in een zeer eenvoudige syntax. Er is een [formele specificatie](https://www.ecma-international.org/wp-content/uploads/ECMA-404_2nd_edition_december_2017.pdf) van deze JSON-syntax. De paragrafen 4 t/m 9 zijn de complete specificatie van de taal. Men gebruikt zogenaamde "railroad diagrams" om uit te leggen waar JSON aan moet voldoen. Zorg dat je [deze korte handleiding] van railroad diagrams doorneemt en dan heel precies begrijpt wat een **valide** JSON-document is.

Een opmerking die wordt gemaakt in de specificatie is dat JSON weliswaar een **syntax** definieert maar dat de bijbehorende **semantiek** (betekenis van de inhoud) niet vastligt. Elke gebruiker van JSON moet afspraken maken of vastleggen over welke data precies gecommuniceerd wordt en wat je er mee kunt. Als je verwacht dat er een lijst van medewerkers wordt verstuurd dan zal de JSON wel een array zijn met daarin objecten. Als je informatie over één persoon opvraagt dan zal de JSON wel een object zijn.

Filmpjes om JSON beter te begrijpen:

- [Web Dev Simplified: Learn JSON in 10 minutes](https://www.youtube.com/watch?v=iiADhChRriM)
- [ByteScout: JSON Specification](https://www.youtube.com/watch?v=Xi1B0EbSgTY)

## jq

Met de tool `jq` kun je data uit JSON-bestanden extraheren. Er is een speciale syntax voor het schrijven van kleine "queries" die aangeven welke data je wil hebben. Bestudeer goed de volgende pagina: <https://www.baeldung.com/linux/jq-command-json>

Filmpjes om JQ beter te begrijpen:

- [Szymon Stepniak: JSON on the command line](https://www.youtube.com/watch?v=FSn_38gDvzM)

Op Windows in Git Bash installeer je `jq` met dit commando:

    curl -L -o ~/bin/jq.exe https://github.com/stedolan/jq/releases/latest/download/jq-win64.exe

Op Mac installeer je `jq` met:

    brew install jq

## Movie data

Via [deze link](https://raw.githubusercontent.com/prust/wikipedia-movie-data/master/movies.json) kun je een bestand downloaden met alle filminformatie die iemand van Wikipedia heeft gehaald. Bestudeer de structuur.

## Opdrachten

1.  Geef een complete UNIX one-liner om alleen de gegevens van de eerste film uit het bestand te laten zien.

2.  Geef een complete UNIX one-liner om alleen de titel van de eerste film uit het bestand te laten zien.

3.  Geef een complete UNIX one-liner om de titels van alle films uit het bestand te laten zien.

## Inleveren

Lever hieronder een PDF in met je uitwerkingen. Gebruik géén titelpagina. Vermeld je naam en studentnummer, en de naam van de opdracht. Vermeld ook de vraag boven elk antwoord---dit mag een samengevatte versie van de vraag zijn.

## Nakijken

De antwoorden worden kritisch nagekeken op zorgvuldige beantwoording. Dat betekent dat de antwoorden gebaseerd moeten zijn op de lesstof, dat wat er staat goed is en logisch onderbouwd en dat er geen onware of irrelevante beweringen of informatie bij de antwoorden staan. Aan de andere kant: een klein foutje is geen probleem.

<!-- ## Links

- http://itsthisforthat.com/api.php?json
- https://ghibliapi.herokuapp.com/
- https://data.rijksmuseum.nl/object-metadata/api/
- https://data.mprog.nl/acquisition/scraping -->
