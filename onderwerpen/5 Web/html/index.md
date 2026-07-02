# HTML for People

Dit is de start van iets heel nieuws.

Je gaat een eigen homepage maken (als je er al eentje hebt, *fine*, dan maak je er nu nog eentje). Volg de hiervoor de cursus op [HTML for People](https://htmlforpeople.com).

Op het moment dat het vaag begint te worden kan het zinvol zijn deze video's te bekijken:

- [CS50 Short: HTML](https://youtu.be/YK78KhMf7bs)
- [CS50 Short: CSS](https://youtu.be/Ub3FKU21ubk)

Zorg dat je homepage helemaal online staat, zoals aangegeven in de cursus.

## Tip over robots.txt

Op een standaard Neocities-website (en veel andere hosting) staat een `robots.txt` bestand dat alle crawlers toegang geeft tot je site. Dit bestand vertelt zoekmachines en andere bots (waaronder tegenwoordig ook AI-crawlers) welke delen van je site ze mogen bezoeken en indexeren. Wil je niet dat jouw homepage opduikt in zoekresultaten of gebruikt wordt om AI-modellen te trainen, pas dan je `robots.txt` aan, bijvoorbeeld:

```
User-agent: *
Disallow: /
```

Let op: `robots.txt` is een verzoek, geen slot op de deur — brave bots houden zich eraan, maar het voorkomt niet dat iemand de site alsnog bezoekt via de directe link.
