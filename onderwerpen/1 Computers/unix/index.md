# UNIX shell

UNIX is een manier om opdrachten aan je computer te geven, meestal via het intikken van de namen van commando's (net zoals Windows een manier is om opdrachten te geven, maar dan door te klikken op bestanden en programma's). Deze workshop bestaat uit twee delen.

Bij de installatie heb je gezien dat je eigen computer ook een Terminal heeft waarin je UNIX-commando's kunt geven. In de komende weken ga je diverse UNIX-commando's leren kennen. Data Scientists gebruiken ook vaak UNIX omdat je daarmee makkelijk vrij complexe operaties op data kunt uitvoeren. Daarover later meer.

## Prompt

Dit is de prompt:

    me@laptop % 

Een "prompt" is een *verzoek om iets in te tikken*. Het systeem geeft je de gelegenheid om een commando op te geven dat uitgevoerd kan worden. Zodra dat uitvoeren gedaan is volgt een nieuwe prompt. De prompt wordt ook wel de "command line" genoemd.

Hieronder vragen we bijvoorbeeld de datum op met het commando date:

    me@laptop ~ % date
    Tue May 10 15:12:18 CEST 2022
    me@laptop ~ % 

Een ander programma om de datum te laten zien is cal. Hiermee verschijnt een kalender van de huidige maand op het scherm (deze wordt "geprint" naar het scherm). Standaard wordt de huidige dag uitgelicht door de voor- en achtergrondkleuren om te wisselen (zie dag 10 hieronder).

me@laptop ~ % cal
      May 2022        
Su Mo Tu We Th Fr Sa  
 1  2  3  4  5  6  7  
 8  9 10 11 12 13 14  
15 16 17 18 19 20 21  
22 23 24 25 26 27 28  
29 30 31              

## Command-line arguments

Veel programma's ondersteunen zogeheten command-line arguments. Dit zijn extra opties die je meegeeft achter de naam van het commando. Zo heeft het programma cal de optie `-3` waarmee de kalenders van de vorige, huidige en volgende maand in één keer wordt geprint naar het scherm:

    me@laptop ~ % cal -3 
                                2022
           April                  May                   June          
    Su Mo Tu We Th Fr Sa  Su Mo Tu We Th Fr Sa  Su Mo Tu We Th Fr Sa  
                    1  2   1  2  3  4  5  6  7            1  2  3  4  
     3  4  5  6  7  8  9   8  9 10 11 12 13 14   5  6  7  8  9 10 11  
    10 11 12 13 14 15 16  15 16 17 18 19 20 21  12 13 14 15 16 17 18  
    17 18 19 20 21 22 23  22 23 24 25 26 27 28  19 20 21 22 23 24 25  
    24 25 26 27 28 29 30  29 30 31              26 27 28 29 30 

Je kunt ook een programma starten dat zelf weer om informatie vraagt. Zo'n vraag heet wederom ook een prompt. Maar omdat je geen commando's kan intikken wordt het géén command line genoemd.
Kijk bijvoorbeeld naar het programma banner. Dit programma wil graag een tekstje hebben dat in zeer grote letters op het scherm geprint wordt. Het programma print daarom `Message:` en wacht tot iets wordt ingetikt. Als je dat doet en op **Enter** drukt, dan gaat het programma pas verder.

    me@laptop ~ % banner -w 32
    Message: hoi     
            #                    #
            ######################
            ######################
                       #
                       ##
            #          ##
            #############
            ###########
                #### 
             ##########
            ##        ## 
            #           #
            #           #
            #          ##
             ###########
              ########
            #           #
            #############   ###
            #############   ###

We geven hier overigens ook de optie `-w 32` mee om te zorgen dat de letters niet al te groot worden. Probeer deze optie gerust eens weg te laten of aan te passen.

## Manual

Hoe kom je er nou achter welke opties een programma ondersteunt? Daarvoor is een speciaal commando "man" in het leven geroepen, dat de handleiding van allerlei programma's kan laten zien. Zo kunnen we de handleiding van "cal" opvragen:

    me@laptop ~ % man cal

Als je dit doet wordt de handleiding op het hele scherm weergegeven. De command line verdwijnt (tijdelijk) en je kunt met de pijltjes op het toetsenbord omlaag en omhoog scrollen om de rest van de tekst te bekijken. Soms kun je zelfs muis of trackpad gebruiken om te scrollen.
 
Als je **q** intikt verdwijnt de handleiding weer en ga je terug naar de command line.

We geven hier de namen van een aantal interessante commando's. Je kunt ze uitproberen en de "man page" opvragen met hulp van het commando `man`.

- whoami
- hostname
- sleep
- leave
- dc

Het nadeel van de man pages is dat er zelden goede voorbeelden gegeven worden, en dat de algemene uitleg vaak overdreven technisch geformuleerd is. Daarvoor kun je beter op internet zoeken. Optie: installeren "tldr" https://tldr.sh

## Vragen

1.  Hoe moet je cal "aanroepen" (welk commando moet je intikken) om een kalender van het huidige jaar te printen, dus alle 12 maanden? Gebruik man.

    <textarea name="form[q1]" rows="8" required></textarea>

2.  Is er nog een manier om de kalender van het hele jaar te printen?

    <textarea name="form[q2]" rows="8" required></textarea>

3.  Wat is het verschil tussen cal en ncal? Lees hiervoor de uitleg in de man page van cal.

    <textarea name="form[q3]" rows="8" required></textarea>

4.  Leg in je eigen woorden uit hoe je één van de bovengenoemde commando's kunt gebruiken.

    <textarea name="form[q4]" rows="8" required></textarea>
