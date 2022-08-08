# Scripting in the shell

Lees het onderdeel "Writing basic scripts" uit het boek *UNIX Visual Quickstart Guide* van Ray & Ray.

Je kunt ook *command-line arguments* gebruiken voor je scripts. Dan kun je echt een commando definiëren dat je vaker kunt gebruiken. Sla bijvoorbeeld het volgende scriptje op als `unquote`:

    sed 's/[“”]/"/g' $1

Hiermee worden "mooie" quotes vervangen door eenvoudige ASCII quotes. Soms is dit handig als je een tekst hebt gekopieerd van een website of uit Word. Vervolgens kun je `unquote` aanroepen met de naam van een bestand:

    unquote imported-text.txt

Jouw script gebruikt dan op de plaats van $1 de opgegeven naam `imported-text.txt`. Het nadeel is dat je script dan echt alleen maar met files werkt. Je kunt dan niet meer dit doen:

    cat alice-in-wonderland.txt | unquote

Hieronder vragen we je om een aantal scripts te schrijven.

1.  Question 1

    <textarea name="form[q1]" rows="8" required></textarea>

1.  Question 7

    <textarea name="form[q7]" rows="8" required></textarea>

1.  Question 14

    <textarea name="form[q14]" rows="8" required></textarea>

1.  Question 17

    <textarea name="form[q17]" rows="8" required></textarea>
