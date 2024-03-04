# Homepage

1. Maak je eigen website met HTML, CSS, and JavaScript,
2. hou goed bij wat je opvalt en wat je leert,
3. en leg in detail van twee problemen uit hoe je ze hebt opgelost.

## Achtergrond

Het internet heeft ongelooflijke dingen mogelijk gemaakt: we kunnen met zoekmachines onderzoek doen naar alles wat we maar kunnen bedenken, we kunnen communiceren met vrienden en familieleden die waar ook ter wereld zijn, games spelen, cursussen volgen en nog veel meer. Toch zijn de websites die we bezoeken gebouwd op slechts drie talen, die elk een specifiek doel dienen:

1. HTML, of _HyperText Markup Language_, die wordt gebruikt om de inhoud van websites te beschrijven;
1. CSS, _Cascading Style Sheets_, die wordt gebruikt om de vormgeving van websites te beschrijven; ander
1. _JavaScript_, dat wordt gebruikt om websites interactief en dynamisch te maken.

In deze opdracht ga jij een profielpagina maken waarop je jezelf, je favoriete hobby of buitenschoolse activiteit, je interesses (muziek, boeken, eten) en/of je motivatie om te leren programmeren deelt met de wereld.

## Om te beginnen

Download de startbestanden:

    curl -OL https://github.com/minprog/webprogrammeren/raw/2020/Problems/2%20profile/profile.zip

Unzip het bestand, en open dan de uitgepakte `index.html` in je webbrowser om te bekijken hoe deze er uit ziet.

## Specificatie

Implementeer in de `profile`-directory een website die:

*   Ten minste vier verschillende `.html`-pagina's bevat, waarvan er ten minste één `index.html` is (de hoofdpagina van je website). Het moet mogelijk zijn om van elke pagina op jouw website naar elke andere pagina te gaan door door één of meer hyperlinks te volgen.

*   `index.html` moet een profielfoto, je naam en een korte beschrijving van jezelf en je interesses bevatten. Als je je niet helemaal op je gemak voelt bij het delen van persoonlijke afbeeldingen of details, je in plaats daarvan bijvoorbeeld een avatarafbeelding kunt gebruiken.

*   De andere pagina's moeten informatie over jou bevatten of iets waarin je geïnteresseerd zou kunnen zijn. Overdrijf het niet, een paar alinea's met een afbeelding is hartstikke goed, of een pagina waar je door een aantal afbeeldingen kunt bladeren, of een soort Javascript-demo (door jezelf aangepast).

*   Gebruik naast `<html>`, `<head>`, `<body>` en `<title>` ten minste tien (10) verschillende HTML-tags. Het meerdere keren gebruiken van een tag (bijv. `<p>`) telt nog steeds als slechts één (1) van die tien!

*   Integreer één of meer functies van Bootstrap in je website. Bootstrap is een populaire bibliotheek (die wordt geleverd met veel kant-en-klare CSS-klassen) waarmee je je site kunt verfraaien. Zie [de documentatie van Bootstrap](https://getbootstrap.com/docs/5.2/) om aan de slag te gaan. Waarschijnlijk is het interessant om een aantal [Bootstrap-componenten](https://getbootstrap.com/docs/5.2/components/) te gebruiken. Om Bootstrap aan je site toe te voegen, volstaat het om de volgende tags in te voegen in de `<head>` van jouw pagina's:

        <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/css/bootstrap.min.css" crossorigin="anonymous">
        <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/js/bootstrap.bundle.min.js" crossorigin="anonymous"></script>

*   Zorg voor ten minste één CSS-bestand dat je zelf schrijft, `styles.css`, waarin je ten minste vijf verschillende CSS-selectors gebruikt (bijv. tag (`example`), class (`.example`) of ID (` #example`)), en waarbinnen je in totaal minimaal vijf (5) verschillende CSS-eigenschappen gebruikt, zoals `font-size` of `margin`.

    Onder de Bootstrap-tags kun je vervolgens een link maken naar deze file:

         <link href="styles.css" rel="stylesheet">

En dan nog optioneel:

*   Integreer één of meer JavaScript-gebaseerde functionaliteiten in je site om deze interactiever te maken. Je kunt JavaScript bijvoorbeeld gebruiken om waarschuwingen toe te voegen, om een steeds herhalend ​​effect te starten, of om interactiviteit toe te voegen aan knoppen, keuzelijsten of formulieren. Wees creatief!

*   Zorg ervoor dat je site er goed uitziet in diverse browsers, zowel op mobiele apparaten als op laptops en desktops.

## Testen

Als je wil zien hoe je site er uitziet terwijl je er aan werkt, hou deze dan geopend in je webbrowser.

Daarnaast kun je in Chrome een mobiele telefoon _simuleren_ door op het telefoonvormige pictogram links van **Elements** in het venster met ontwikkelaarstools te klikken of, als je het tabblad Developer Tools hebt geopend, door `Ctrl`+`Shift`+`M` op een PC of `Cmd`+`Shift`+`M` op een Mac te tikken. Dit is vaak handiger dan de site bezoeken via je eigen mobiele telefoon.

## Assessment

Je website wordt beoordeeld op basis van het feit of deze voldoet aan de vereisten van de specificatie zoals hierboven uiteengezet, en of de HTML netjes en correct is. Om ervoor te zorgen dat je pagina's correct zijn, kun je de [Markup Validation Service](https://validator.w3.org/#validate_by_input) gebruiken door door de HTML-code rechtstreeks in het daarvoor bestemde tekstvak te kopiëren en te plakken. Zorg ervoor dat je **alle** waarschuwingen of fouten die door de validator worden voorgesteld, oplost voordat je je opdracht instuurt!

Let ook op:

* of de vormgeving van je website zodanig is dat bediening en navigatie eenvoudig zijn voor een relatief onervaren gebruiker;
* of de CSS echt in een aparte file staat zoals hierboven beschreven, en er dus helemaal geen CSS-code in de HTML-code staat; en
* of je overbodige herhaling zoveel mogelijk hebt ingeperkt door gebruik te maken van het "cascading" principe van CSS, waarbij stijl op een bepaald element ook doorwerkt op de "child"-elementen.

Qua stijl is het aan jou om de HTML tags netjes te indenteren en overzichtelijk te houden. Bovendien kun je ook in HTML comments plaatsen op deze manier:

        <!-- Comment goes here -->

Maar het commenten van HTML is niet zo belangrijk als commenten in bijvoorbeeld C-code, omdat de inhoud van HTML vaak al aardig beschrijft wat er aan de hand is. Ook in CSS kun je comments achterlaten, maar dan op de volgende manier:

        /* Comment goes here */

## Hints

Zorg dat je de voorbeelden in het college goed bestudeert en van daaruit je website gaat uitbouwen. 
Voor uitgebreide details over HTML, CSS en JS kun je kijken op de volgende pagina's:

* [HTML](https://www.w3schools.com/html/)
* [CSS](https://www.w3schools.com/css/)
* [JavaScript](https://www.w3schools.com/js/)

## Reflectievraag

Beschrijf uitgebreid twee problemen die je bent tegengekomen tijdens het maken van je Homepage en hoe je die problemen toen hebt opgelost. Dit is dus een beschrijving van je ontwikkelproces, met verwijzingen naar inhoud van de stof; het gaat daarbij niet om problemen met het begrijpen van bedoeling van de opdracht zelf, maar met de stof, dus hoe HTML, CSS en JS precies werken of juist niet werken.

## Checkup

- Controleer of je voldoet aan de minimumeisen zoals het aantal pagina's, verschillende gebruikte tags, enzovoort.
- Controleer of alle HTML-pagina's zonder foutmeldingen door de HTML validator komen. Ook "waarschuwingen" kunnen en moeten opgelost zijn vóór inleveren.
