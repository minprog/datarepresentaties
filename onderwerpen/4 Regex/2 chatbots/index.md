# Chatbots met reguliere expressies

1. Implementeer een simpele chatbot,
2. formuleer regels met hulp van reguliere expressies,
3. en bewonder het resultaat!

## ELIZA

In het hoofdstuk van Jurafsky en Martin heb je gezien dat de computertherapeut ELIZA geheel geïmplementeerd kan worden met hulp van reguliere expressies. In feite worden hier allerlei **regels** verzameld die op volgorde toegepast kunnen worden.

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/RMK9AphfLco" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

Hoewel menselijke communicatie meestal flexibeler is dan het zuiver toepassen van strakke regels, is het vatten van allerlei patronen wel een succesvolle strategie om een prototype van een chatbot te implementeren. Nog sterker, het analyseren van potentiële patronen en hiervan een programma maken helpt je beter begrijpen hoe zo'n gesprek vorm krijgt.

## Eigen implementatie

Als eerste stap ga je een uitgebreidere versie van ELIZA implementeren. Maak een file `eliza.sh` en voeg daar deze regels aan toe:

    #!/bin/bash

    echo "Please tell me what's been bothering you."
    while read sentence; do
      echo "$sentence" | tr 'a-z' 'A-Z' | sed -E -f eliza.sed
    done

Dit script doet niets anders dan telkens weer om input vragen en dan `sed` aanroepen met een bestand waarin alle regels beschreven zijn. Hierdoor wordt steeds een nieuw antwoord gegenereerd op basis van de input van de gebruiker en het toepassen van zo'n regel.

Maak ook een bestand `eliza.sed` om de regels in te plaatsen. Neem de volgende regels over. Ze zijn een heel klein beetje anders dan de regels op pagina 10 in het boek van Jurafsky. Kun je bedenken waarom we ze gewijzigd hebben?

    s/.*I'M (DEPRESSED|SAD).*/I AM SORRY TO HEAR YOU ARE \1/
    s/.*I AM (DEPRESSED|SAD).*/WHY DO YOU THINK YOU ARE \1/
    s/.*ALL .*/IN WHAT WAY/
    s/.*ALWAYS .*/CAN YOU THINK OF A SPECIFIC EXAMPLE/

Om het script te starten run je `bash eliza.sh` en stoppen kan met **Ctrl-C**. Op dit moment zijn maar vier regels actief.

Jouw opdracht is om online ELIZA simulators uit te proberen en te bekijken welke regels er nog zouden kunnen zijn. Voeg een aantal van deze regels toe aan jouw versie van `eliza.sed`. Zorg dat je minstens nog 3 regels vindt waarin een woord uit de input gebruikt wordt in de output, zoals regels 1 en 2 uit de voorbeelden hierboven. En dan nog een aantal simpeler regels, zoals regels 3 en 4 in de voorbeelden hierboven.

## Jouw bot

Als tweede stap ga je een eigen bot maken die op dezelfde manier werkt maar een ander doel heeft dan Rogeriaanse therapeut spelen. Denk bijvoorbeeld aan:

- Een student helpen met een programmeeropdracht in C
- Iemand helpen kiezen om wel of niet naar de kroeg te gaan
- Ideeën opdoen voor op vakantie gaan met of zonder veel budget
- ...

Het probleem is wel dat je geen "geheugen" hebt. Als je een antwoord formuleert dan is dat alleen gebaseerd op de huidige input, en niet op wat er eerder gezegd is. Maar dat geeft niet, het gaat vooral om het oefenen met reguliere expressies!

Je hoeft niet meer dan 8 regels te gebruiken, het gaat uiteindelijk om nadenken over die regels en het oefenen met het schrijven van reguliere expressies.
