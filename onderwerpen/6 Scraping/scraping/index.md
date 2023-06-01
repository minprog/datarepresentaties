# Scraping

1. Bestudeer onderstaande uitleg over Scraping,
2. en de materialen die gelinkt zijn,
3. en hou goed bij wat je opvalt en wat je leert.

## Pup

Lees de [README](https://github.com/EricChiang/pup) van de tool `pup`. Met deze tool kun je informatie scrapen uit HTML-pagina's. Zo kun je informatie van een website laten zien in je terminal, maar je kunt dit ook gebruiken voor bijvoorbeeld dataverzameling voor onderzoek.

Installatie voor Ubuntu en WSL:

    curl -LO https://github.com/ericchiang/pup/releases/download/v0.4.0/pup_v0.4.0_linux_amd64.zip
    unzip pup_v*

Dit geeft in de huidige directory een executable genaamd `pup` die je zoals normaal kunt runnen met `./pup`. Je kunt het programma dus niet runnen door alleen `pup` in te tikken. Pas dit aan in de voorbeelden hieronder! Als pup helemaal niet werkt, stuur even een mail naar <help@mprog.nl>.

Installatie voor Mac:

    brew install pup

Dit installeert een commando `pup` dat je kunt aanroepen met `pup` (anders dan op Windows dus!).

Om Pup uit te testen met websites kun je `curl` gebruiken voor het binnenhalen van de pagina en het resultaat via een pipe doorsturen naar pup. Als voorbeeld kun je op deze pagina de pagina van het KNMI binnen halen en "netjes" uitprinten:

    curl -s 'https://www.knmi.nl/home' | pup -c

Met de optie `-s` voor `curl` zorgen we ervoor dat het programma geen "downloading" indicator geeft. Die is ook niet echt interessant omdat het laden van de meeste HTML-pagina's maar heel kort duurt. Met de optie `-c` voor `pup` zorgen we ervoor dat de output in kleur wordt weergegeven. Die kun je weglaten als je wilt.

## CSS

Scraping met `pup` gaat op basis van de selectors die ook in CSS gebruikt worden. Hiermee kun je aangeven welk deel van de HTML je wilt hebben.

In een vorige module heb je kennis gemaakt met CSS, maar je hebt hier nog niet systematisch mee geoefend. Ga naar [deze website om extra te oefenen](https://flukeout.github.io/). Zorg dat je de belangrijkste CSS-selectors kent. Op de GitHub-pagina van `pup` staat ook een lijstje van de ondersteunde CSS-selectors in deze tool.

## Opdrachten

Geef steeds de complete pipeline inclusief het gebruikte `curl`-commando, pipes en andere commando's.

1.  Zoek uit hoe je alle `span`s met de class `green` kunt scrapen van de pagina <https://www.pythonscraping.com/pages/warandpeace.html>.

1.  Zoek uit hoe je <u>alleen de tekst</u> van bovenstaande `span`s kunt scrapen.

1.  Zoek uit met welk commando (curl + pup) je alle URL's (links) naar het laatste nieuws van de NOS kunt scrapen. Gebruik hiervoor de pagina <https://nos.nl/nieuws>.

1.  Zoek uit hoe je alle headlines kunt scrapen, dus de koppen van het nieuws.

1.  Zoek uit hoe je een korte omschrijving van het weer kunt printen vanuit de website van het KNMI.

1.  Zoek uit hoe je alle `tr` elementen uit de tabel op <https://pythonscraping.com/pages/page3.html> kunt scrapen, maar met uitzondering van het eerste `tr`-element (deze bevat de tabelkopjes en die hebben we niet nodig). In de README van Pup staan de selectors die je kunt gebruiken. Volg de link naar MDN om uit te zoeken hoe ze werken.

1.  Extra opdracht (optioneel): zoek uit hoe je een JSON kunt genereren met daarin alle links en headlines als paren. Zo'n paar ziet er dan zo uit:

        {
          "href": "/artikel/2441789-vogelspin-ontsnapt-op-kinderdagverblijf-velp",
          "text": "Vogelspin ontsnapt op kinderdagverblijf Velp"
        }

    Omdat het een lijst van paren is verwachten we dat hele de JSON een array is, dus begint met `[` en eindigt met `]`.

## Inleveren

Lever hieronder een PDF in met je uitwerkingen. Gebruik géén titelpagina. Vermeld je naam en studentnummer, en de naam van de opdracht. Vermeld ook de vraag boven elk antwoord---dit mag een samengevatte versie van de vraag zijn.

## Nakijken

De antwoorden worden kritisch nagekeken op zorgvuldige beantwoording. Dat betekent dat de antwoorden gebaseerd moeten zijn op de lesstof, dat wat er staat goed is en logisch onderbouwd en dat er geen onware of irrelevante beweringen of informatie bij de antwoorden staan. Aan de andere kant: een klein foutje is geen probleem.