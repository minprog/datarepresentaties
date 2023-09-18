# Reguliere expressies

1. Gebruik onderstaande vragen om goed te begrijpen hoe regexes werken,
2. en hou goed bij wat je opvalt en wat je leert.

## Waarschuwing

Let op: als je testbestanden maakt, doe dat dan niet in Windows met Notepad of Atom. Gebruik in plaats daarvan nano (zoals uitgelegd in de Software Carpentry workshop). Dan zijn de line endings correct voor gebruik van grep.

## Aanpak

Voor deze opdrachten moet je reguliere expressies schrijven en voorbeelden geven die wél en niet werken. Je moet hiervoor `grep` gebruiken zoals in gedemonstreerd in de workshops. Gebruik de UNIX manual pages op jouw systeem om te juiste opties (flags) te vinden die je nodig hebt. Vermeld de volledige commando's die op jouw computer echt werken.

Er wordt hieronder ook gevraagd naar **edge cases**. Dit zijn de voorbeelden waar je het uiterste vraagt van de reguliere expressie. Stel dat je een commando moet geven om alle woorden met een letter `a` erin te vinden; dan wil je zeker checken of een woord met daarin *alleen* de letter `a` (en niets anders) óók correct matcht. In sommige gevallen kan het zinvol zijn om te kijken of een match aan het begin of eind van een regel ook correct werkt en niet alleen in het midden. Welke edge case zinvol is hangt af van de reguliere expressie. Het vermelden van edge cases doe je zo goed mogelijk, maar als je een paar edge cases mist is dit geen probleem.

## Regels

In de volgende opgaven ga je op zoek naar **regels** die matchen. De input is een bestand met meerdere regels en de output zijn de regels (zinnen) waarin een match voorkomt.

1.  Geef een compleet grep-commando waarmee je elke regel selecteert waar aan het eind van de regel een punt (`.`) staat. Geef een aantal voorbeeldzinnen die matchen en een aantal zinnen die niet matchen, waaronder edge cases.

2.  Geef een compleet grep-commando waarmee je elke regel selecteert waarin de string `the` (of `The`) staat. `There is nothing.` moet ook matchen. Geef een aantal voorbeeldzinnen die matchen en een aantal zinnen die niet matchen, waaronder edge cases.

3.  Geef een compleet grep-commando waarmee je elke regel selecteert waarin het woord (dus niet de string) `we` staat. Geef een aantal voorbeeldzinnen die matchen en een aantal zinnen die niet matchen, waaronder edge cases.

4.  Geef een compleet grep-commando waarmee je elke regel selecteert die met `A`, `D` of `W` begint. Geef een aantal voorbeeldzinnen die matchen en een aantal zinnen die niet matchen, waaronder edge cases.

5.  Geef een compleet grep-commando waarmee je elke regel selecteert waarin een `o` staat gevolgd door één of meer `r`. Geef een aantal voorbeeldzinnen die matchen en een aantal zinnen die niet matchen, waaronder edge cases.

6.  Geef een compleet grep-commando waarmee je elke regel selecteert waarin een vraagteken óf een backslash staan. Geef een aantal voorbeeldzinnen die matchen en een aantal zinnen die niet matchen, waaronder edge cases.

## Strings

In de volgende opgaven ga je op zoek naar **strings** die matchen. De input is een bestand met tekst, eventueel met meerdere regels, en de output zijn de losse strings (delen) die matchen. Hiervoor gebruik je normaal de optie `-o` van `grep`. Je kunt deze ook combineren met de optie `-w` om alleen strings te matchen die een heel woord zijn.

1.  Geef een compleet grep-commando waarmee je elke string selecteert die bestaat uit het woord `we`. Geef een aantal voorbeeldteksten met matchen en markeer duidelijk welke delen een match zijn. Kijk zoals altijd naar edge cases en geef ook teksten die geen matches bevatten.

2.  Geef een compleet grep-commando waarmee je elke string selecteert die begint met "Wachtwoord" en eindigt met een viercijferig getal. Hoofd- of kleine letters mogen allebei. Geef een aantal voorbeeldteksten met matchen en markeer duidelijk welke delen een match zijn. Kijk zoals altijd naar edge cases en geef ook teksten die geen matches bevatten.

3.  Geef een compleet grep-commando waarmee je elk woord selecteert dat met `A`, `D` of `W` begint. Geef een aantal voorbeeldteksten met matchen en markeer duidelijk welke delen een match zijn. Kijk zoals altijd naar edge cases en geef ook teksten die geen matches bevatten.

4.  Geef een compleet grep-commando waarmee je elk woord selecteert waarin een `o` staat gevolgd door één of meer `r`. Geef een aantal voorbeeldteksten met matchen en markeer duidelijk welke delen een match zijn. Kijk zoals altijd naar edge cases en geef ook teksten die geen matches bevatten.

## De reflectievraag

Om te laten zien dat je deze opdracht met voldoende inspanning hebt gemaakt en daarvan hebt geleerd, vragen we je te reflecteren op het maken van de opdracht en het bestuderen van het materiaal. Dit doen we om een aantal redenen:

* Je laat zien dat je actief aan de slag bent gegaan met de opdracht en daardoor leert.
* Je laat zien wat je leert en hoe je dat doet. Hier zijn wij als docenten natuurlijk super benieuwd naar!
* Je laat zien dat je niet alle antwoorden oppervlakkig googled of laat genereren met generatieve AI (chatGPT).

Kort gezegd, met deze vraag toon je aan dat jij de punten voor de opdracht verdient. Dat doe je door in je antwoord concreet te noemen:

* Wat je moeilijk vond bij de opdracht. Wat was er onverwachts of anders? Waar liep je tegenaan?
    * Noem hier echte voorbeelden met genoeg detail. Dus niet: "onderwerp X is lastig". Noem juist wat er precies lastig was en hoe je daaruit kwam.
* Welke bronnen je hebt gebruikt om verder te komen en uit te zoeken wat je moest begrijpen.
    * Laat zien welke bronnen je gebruikt om een vraag te beantwoorden. Dat hoeven geen wetenschappelijke bronnen te zijn. Wees wel precies in hoe je de bronnen gebruikt. Bijvoorbeeld niet: "Heb ik opgezocht in het boek", maar liever:
        * "De uitleg over hoe hexadecimaal rekenen werkt vond ik in hoofdstuk 4.1".
        * "Ik begreep uit het boek niet wat floppy disks zijn. In dit filmpje (https://youtube.com/...) wordt het beter uitgelegd".

Je snapt dat je zonder uitgebreid antwoord op deze vraag ook geen punten kan halen voor de opdracht.

> Tip: je kunt voor zo'n praktische opdracht als deze ook screenshots maken en opnemen in je PDF om te laten zien wat er bijvoorbeeld mis ging.

## Inleveren

Lever een PDF in met je uitwerkingen. Gebruik géén titelpagina. Vermeld je naam en studentnummer, en de naam van de opdracht. Vermeld ook de vraag boven elk antwoord---dit mag een samengevatte versie van de vraag zijn. Als je informatie van buiten de aangeleverde tekst gebruikt moet je een bronvermelding doen; je mag gewoon de site/titel noemen in de tekst.
