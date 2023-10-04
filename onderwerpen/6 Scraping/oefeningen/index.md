# Oefeningen

Deze vragen zijn goede oefeningen voor het tentamen. De verwachting is dat je alle vragen op het tentamen correct beantwoordt, foutjes daargelaten. Je hebt dus parate kennis nodig van de regels die je nodig hebt om via `pup` informatie uit een HTML-pagina te extraheren.

Je kunt onderstaande oefeningen niet inleveren en ze horen dus ook niet bij de deadline voor de Scraping-module.

Onderstaande vragen zijn *grotendeels* representatief voor de vragen die je op het tentamen tegen zou kunnen komen, maar je zou ook vragen tegen kunnen komen die meer lijken op de vragen bij de [Scraping-opdracht](/tools/scraping). Er zullen geen vragen zijn over `jq` en JSON.

Wat je moet weten voor het tentamen:

- Hoe je elementen kunt selecteren op basis van tag-naam, id, class of andere attributen.
- Hoe je selectors kunt combineren om op meerdere eigenschappen te selecteren.
- Hoe je selectors kunt combineren om specifieke onderdelen van een document te selecteren.

## HTML

Gegeven is het volgende HTML-document in `sample.html`:

    <!DOCTYPE html>
    <html>
    <head>
      <title>Sample HTML Document</title>
    </head>
    <body>
      <h1>Welcome to my website</h1>
      <div class="container">
        <p>Here is some text in a paragraph.</p>
        <ul>
          <li>Item 1</li>
          <li>Item 2</li>
          <li>Item 3</li>
        </ul>
        <div class="highlight">
            <p>Here is some highlighted text in a paragraph.</p>
            <p>Here is some more highlighted text in a paragraph.</p>
        </div>
        <ul id="done">
          <li>Item 4</li>
          <li>Item 5</li>
          <li>Item 6</li>
        </ul>
      </div>
      <div class="footer">
        <p>Copyright © 2021</p>
      </div>
    </body>
    </html>

Geef **complete pup-commando's** om de volgende vragen te beantwoorden. Gebruik altijd selectors die net zo specifiek zijn als de vraag zegt! Je selectors moeten ook op andere HTML-documenten werken.

1. Geef een commando om de eerste `<p>` tag in elke eerste `<div>` te selecteren. In het document hierboven matcht dan alleen de `<p>Here is some text in a paragraph.</p>`.

2. Geef een commando om de tweede `<li>` tag in elke `<ul>` te selecteren. Hierboven matchen dan `<li>Item 2</li>` en `<li>Item 5</li>`.

3. Geef een commando om de `<p>` tags in elke `<div class="highlight">` te selecteren. Hierboven matchen dan `<p>Here is some highlighted text in a paragraph.</p>` en `<p>Here is some more highlighted text in a paragraph.</p>`.

4. Geef een commando om de laatste tag in de `<ul id="done">` te selecteren. Hierboven matcht dan `<li>Item 6</li>`.

5. Geef een commando om elke `<title>` tag selecteren. Hierboven matcht dan `<title>Sample HTML Document</title>`.
