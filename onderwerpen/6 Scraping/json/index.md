# JSON en cURL

1. Bestudeer onderstaande uitleg over JSON en cURL,
2. en de materialen die gelinkt zijn,
3. en hou goed bij wat je opvalt en wat je leert.

## Het JSON tekst-formaat

JSON is een formaat om informatie uit te drukken in simpele tekst. Je kunt het in de praktijk gebruiken om data uit te wisselen. Sommige websites bieden dan ook de mogelijkheid om data op te vragen in JSON-formaat, vaak zodat je die data kunt gebruiken om een andere website mee te bouwen.

JSON is een soort tegenhanger van een ouder formaat, XML. XML biedt ongeveer de zelfde mogelijkheden maar de syntax (manier van schrijven) is veel ingewikkelder. In de praktijk kunnen de meeste toepassingen prima gebruik maken van alleen maar JSON.

## Structuren

Er zijn twee soorten structuren in JSON, namelijk *objecten* en *arrays*. Een object ziet er misschien zo uit:

    {
        "eigenschap1": "waarde1",
        "eigenschap2": "waarde2"
    }

En een array met daarin strings en getallen ziet er zo uit:

    [
        "informatie_in_een_string_1",
        "informatie_in_een_string_2",
        19291,
        319,
        "informatie_in_een_string_3"
    ]

Het gaat hier om de schrijfwijze, dus hoe je de haakjes en de aanhalingstekens moet plaatsen.

## Hiërarchie

Belangrijk in JSON is dat structuren ook andere structuren kunnen bevatten. Dit maakt dat je *hierarchiën* kunt beschrijven in JSON. Zo kun je een rijtje van objecten vatten in een array. Denk aan een lijst van medewerkers, waar elke medewerker ook weer een aantal eigenschappen heeft, zoals een naam en een huisnummer.

Hieronder vind je een *array* met daarin twee *objecten*. Elk object heeft daarin twee attributen (eigenschappen), namelijk `name` en `address`. De waarde van `address` is ook weer een object, met daarin twee attributes, `street` en `number`.

    [
        {
            "name": "Ford Prefect",
            "address": {
                "street": "Science Park",
                "number": 900
            },
            "phones": [ "0600822729", "0600187327" ]
        },
        {
            "name": "Arthur Dent",
            "address": {
                "street": "Science Park",
                "number": 900
            },
            "phones": [ "0600181456", "0600783102" ]
        }
    ]

Naast arrays en objects zijn er nog slechts twee soorten informatie in JSON (twee types), namelijk *numbers* en *strings*. In het voorbeeld hierboven zijn `name` en `street` allebei strings, en `number` is een number. Let op dat de telefoonnummers strings zijn in dit geval!

## Syntax en semantiek

JSON heeft een vaste **syntax** zoals hierboven beschreven. De **semantiek**, ofwel de betekenis van de inhoud, ligt niet vast. Elke schrijver van een JSON-document moet afspraken maken of vastleggen over welke data precies gecommuniceerd wordt en wat je er mee kunt. Als je verwacht dat er een lijst van medewerkers wordt verstuurd dan zal de JSON wel een array zijn met daarin objecten. Als je informatie over één persoon opvraagt dan zal de JSON wel een object zijn met daarin diverse eigenschappen.

Filmpjes om JSON beter te begrijpen:

- [Web Dev Simplified: Learn JSON in 10 minutes](https://www.youtube.com/watch?v=iiADhChRriM)
- [ByteScout: JSON Specification](https://www.youtube.com/watch?v=Xi1B0EbSgTY)

## jq

Met de tool `jq` kun je data uit JSON-bestanden extraheren. Er is een speciale syntax voor het schrijven van kleine "queries" die aangeven welke data je wil hebben. Bestudeer goed de volgende pagina: <https://www.baeldung.com/linux/jq-command-json>

Filmpjes om JQ beter te begrijpen:

- [Szymon Stepniak: JSON on the command line](https://www.youtube.com/watch?v=FSn_38gDvzM)

Op Windows in WSL installeer je `jq` met dit commando:

    curl -L -o ~/.local/bin/jq.exe https://github.com/stedolan/jq/releases/latest/download/jq-win64.exe

Op Mac installeer je `jq` met:

    brew install jq

## Movie data

Via [deze link](https://raw.githubusercontent.com/prust/wikipedia-movie-data/master/movies.json) kun je een bestand downloaden met alle filminformatie die iemand van Wikipedia heeft gehaald. Bestudeer de structuur.

## Opdrachten

In de volgende opdrachten werkt je met het gedownloade bestand `movies.json`.

1.  Geef een complete UNIX one-liner (met `cat` en `jq`) om alleen de gegevens van de eerste film uit het bestand te laten zien.

2.  Geef een complete UNIX one-liner (met `cat` en `jq`) om alleen de titel van de eerste film uit het bestand te laten zien.

3.  Geef een complete UNIX one-liner (met `cat` en `jq`) om de titels van alle films uit het bestand te laten zien.

<!-- ## Links

- http://itsthisforthat.com/api.php?json
- https://ghibliapi.herokuapp.com/
- https://data.rijksmuseum.nl/object-metadata/api/
- https://data.mprog.nl/acquisition/scraping -->

## cURL

Gebruik `curl` om de HTML van een webpagina op te vragen. Zo kun je bijvoorbeeld de HTML van zoekmachine DuckDuckGo krijgen:

    curl -s https://duckduckgo.com/

We gebruiken `-s` ofwel "silent" om te zorgen dat `curl` geen download-indicator laat zien. Bij het ophalen van eenvoudige webpagina's hebben we die niet nodig.

## JSON via cURL

We kunnen ook JSON-data opvragen via `curl`, als iemand deze data op een website beschikbaar stelt. Vraag eens de locatie van het International Space Station op:

    curl -s https://api.wheretheiss.at/v1/satellites/25544

Je ziet dan meteen dat je JSON als antwoord krijgt in plaats van HTML.

    {"name":"iss","id":25544,"latitude":-24.135574363392,"longitude":-111.86401960141,"altitude":425.37210858971,"velocity":27557.51464498,"visibility":"eclipsed","footprint":4534.693976796,"timestamp":1659509744,"daynum":2459794.7887037,"solar_lat":17.482788938462,"solar_lon":77.627649838076,"units":"kilometers"}

Om de JSON een beetje leesbaar te krijgen kun je deze **doorsturen** van `curl` naar `jq`:

    curl -s https://api.wheretheiss.at/v1/satellites/25544 | jq

Dan wordt de JSON zo op het scherm geprint:

    {
      "name": "iss",
      "id": 25544,
      "latitude": -28.483617342432,
      "longitude": -107.62821176958,
      "altitude": 427.23022766961,
      "velocity": 27552.819683785,
      "visibility": "eclipsed",
      "footprint": 4544.0662041756,
      "timestamp": 1659509837,
      "daynum": 2459794.7897801,
      "solar_lat": 17.482507366243,
      "solar_lon": 77.240127963861,
      "units": "kilometers"
    }

## Rate limits

Let op dat veel API's een **rate limit** hebben. Dat betekent dat je niet al te vaak een verzoek mag sturen (vanaf hetzelfde IP-adres), om misbruik te voorkomen. Zelfs als je met de hand, vanaf de terminal, aan het experimenteren bent kan dit gebeuren. Als je echt veel gaat experimenteren kun je de JSON ook even opslaan op je eigen computer:

    curl -s https://api.wheretheiss.at/v1/satellites/25544 > iss.json

Dan kun je `jq` zo gebruiken:

    cat iss.json | jq '.'

Deze omweg is niet altijd nodig.

## Opdrachten

4.  Geef een commando met `curl` en `jq` om alleen de latitude én longitude uit te printen. Het resultaat zou er zo uit moeten zien (met andere getallen natuurlijk!):

        -41.536613527854
        -90.033171572304

    In de documentatie van `jq` die we hierboven hebben gelinkt moet je kunnen vinden hoe je twee van die waarden eruit filtert. Zorg dat dit lukt voordat je verder gaat.
{:start="4"}

## Inleveren

Lever hieronder een PDF in met je uitwerkingen. Gebruik géén titelpagina. Vermeld je naam en studentnummer, en de naam van de opdracht. Vermeld ook de vraag boven elk antwoord---dit mag een samengevatte versie van de vraag zijn.

## Nakijken

De antwoorden worden kritisch nagekeken op zorgvuldige beantwoording. Dat betekent dat de antwoorden gebaseerd moeten zijn op de lesstof, dat wat er staat goed is en logisch onderbouwd en dat er geen onware of irrelevante beweringen of informatie bij de antwoorden staan. Aan de andere kant: een klein foutje is geen probleem.
