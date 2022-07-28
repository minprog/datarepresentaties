# Scraping

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
