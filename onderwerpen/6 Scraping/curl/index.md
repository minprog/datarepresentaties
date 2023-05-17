# cURL

1. Bestudeer onderstaande uitleg over cURL,
2. en de materialen die gelinkt zijn,
3. en hou goed bij wat je opvalt en wat je leert.

## Over cURL

Gebruik `curl` om de HTML van een webpagina op te vragen. Zo kun je bijvoorbeeld de HTML van zoekmachine DuckDuckGo krijgen:

    curl -L duckduckgo.com

Dit commando stuurt standaard een verzoek naar de server http://duckduckgo.com, dus via het HTTP-protocol. Nu worden tegenwoordig bijna alle websites bij voorkeur via HTTPS gebruikt. Daarom stuurt de server in dat geval als antwoord dat de pagina te vinden is op https://duckduckgo.com/ en dat het verzoek dáárheen gestuurd moet worden. De optie `-L` zorgt ervoor dat bij zo'n antwoord alsnog de juiste pagina wordt opgevraagd (zolang de server maar zegt welke het moet zijn).

## JSON via cURL

In de volgende module gaan we aan de slag met HTML maar nu gaan we eerst JSON-data opvragen via `curl`. Vraag eens de locatie van het International Space Station op:

    curl https://api.wheretheiss.at/v1/satellites/25544

Je ziet dan meteen dat je JSON als antwoord krijgt in plaats van HTML.

    {"name":"iss","id":25544,"latitude":-24.135574363392,"longitude":-111.86401960141,"altitude":425.37210858971,"velocity":27557.51464498,"visibility":"eclipsed","footprint":4534.693976796,"timestamp":1659509744,"daynum":2459794.7887037,"solar_lat":17.482788938462,"solar_lon":77.627649838076,"units":"kilometers"}

Om de JSON een beetje leesbaar te krijgen kun je deze **doorsturen** van `curl` naar `jq`:

    curl https://api.wheretheiss.at/v1/satellites/25544 | jq '.'

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

    curl https://api.wheretheiss.at/v1/satellites/25544 > iss.json

Dan kun je `jq` zo gebruiken:

    cat iss.json | jq '.'

## Oefenvraag

Geef een commando om alleen de latitude én longitude uit te printen. Het resultaat zou er zo uit moeten zien (met andere getallen natuurlijk!):

        -41.536613527854
        -90.033171572304

Zorg dat dit lukt voordat je verder gaat.
