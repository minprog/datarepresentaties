# Week 6: Web

What's the difference between syntax and semantics? How is semantics annotated in HTML and what alternatives are there? How can HTML be seen as a hierarchical structure?


## 1.2 Homepage

Create a Homepage for yourself on Github Pages.

## 1.3 DOM

- Laten zien met diagram dat het een hiërarchie is
- In de inspector openen en uitklappen
- "Add child" via de inspector
- DOM-manipulatie in web console
- CSS selectors (worden ook gebruikt in pup, zie onder)

## 1.4 Scraping

Pup: https://github.com/EricChiang/pup

alle headlines, links en combineren met paste

    curl "https://nos.nl/nieuws" | pup -c "a.list-items__link attr{href}" > headline.links.txt
    curl "https://nos.nl/nieuws" | pup -c "h3.list-items__title text{}" > headline.texts.txt
    paste -d "\n" headline.links.txt headline.texts.txt

alle headline-informatie en dan extracten met jq

    curl "https://nos.nl/nieuws" | pup -c "a.list-items__link json{}" > headlines.json
    < headlines.json jq '.[] | {href:.href, text:.children[0].children[0].text}

Bovenstaande is niet per se valid json, [] ontbreekt als top-level list'

    < headlines.json jq '[.[] | {href:.href, text:.children[0].children[0].text}]'
