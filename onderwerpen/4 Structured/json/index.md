# JSON-formaat

JSON is een formaat om hierarchische structuren uit te drukken in simpele tekst. Je kunt het in de praktijk gebruiken om data uit te wisselen. Sommige websites bieden dan ook de mogelijkheid om data op te vragen in JSON-formaat.

JSON is een soort tegenhanger van een ouder formaat, XML. XML biedt ongeveer de zelfde mogelijkheden maar de syntax (manier van schrijven) is veel ingewikkelder. Je kunt ook zeggen dat je met XML preciezer kunt zijn, maar in de praktijk is JSON voor heel veel toepassingen meer dan voldoende.

## Hiërarchie

De basis van JSON is dat je twee soorten structuren hebt die weer andere structuren kunnen bevatten. Dit zijn objecten en arrays. Het feit dat structuren andere structuren bevatten maakt dat je hierarchiën kunt beschrijven in JSON.

Zo kun je een rijtje van objecten vatten in een array (denk aan een lijst van medewerkers). En je kunt een object "eigenschappen" meegeven waarin je weer andere waarden stopt (denk aan een persoon die een naam heeft en een huisnummer).

## Syntax

Dit alles wordt gevat in een zeer eenvoudige syntax. Er is een [formele specificatie](https://www.ecma-international.org/wp-content/uploads/ECMA-404_2nd_edition_december_2017.pdf) van deze JSON-syntax. De paragrafen 4 t/m 9 zijn de complete specificatie van de taal. Men gebruikt zogenaamde "railroad diagrams" om uit te leggen waar JSON aan moet voldoen. Zorg dat je [deze korte handleiding] van railroad diagrams doorneemt en dan heel precies begrijpt wat een **valide** JSON-document is.

Een opmerking die wordt gemaakt in de specificatie is dat JSON weliswaar een **syntax** definieert maar dat de bijbehorende **semantiek** (betekenis van de inhoud) niet vastligt. Elke gebruiker van JSON moet afspraken maken of vastleggen over welke data precies gecommuniceerd wordt en wat je er mee kunt. Als je verwacht dat er een lijst van medewerkers wordt verstuurd dan zal de JSON wel een array zijn met daarin objecten.

In feite geldt hetzelfde voor CSV: ook daar kun je niet aan de data ontlenen wat er bedoeld wordt.
