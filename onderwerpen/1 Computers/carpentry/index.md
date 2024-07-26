# Bestandssysteem in UNIX

Deze pagina bevat oefenmaterialen om je voor te bereiden voor het tentamenonderdeel "UNIX-commando's en bestandssysteem".

## Voorbereiding

Lees het hoofdstuk 5 "File systems" uit het boek van Dale & Lewis, *Computer Science Illuminated*. (Let op: in de reader staat eerst nog diverse andere hoofdstukken, maar die komen later.)

## Workshop

Gebruik de website van [Software carpentry](https://swcarpentry.github.io/shell-novice/) om de workshop te doen.

1.  Zorg dat je een UNIX-omgeving klaar hebt staan op je computer. Je hebt deze bij Programmeren 1 geinstalleerd. (Gebruik *niet* de installatie-instructies van Software Carpentry.)

    - Op een Mac gebruik je de terminal-applicatie om de workshop te volgen.
    - Op Windows gebruik je Ubuntu om de workshop te volgen.

    Mocht je niet meer weten hoe dit werkt, kom dan langs in het lab en betrek een assistent erbij.

2.  Vergeet niet om op de Setup-pagina van de workshop de **zip-file** te downloaden waarin alle bestanden staan om mee te oefenen.

3.  Doe alle oefeningen van **hoofdstukken 1, 2 en 3**. Het doel is om goed voorbereid te zijn voor de komende weken. Je doet dit door goed te oefenen en commando's **over te tikken** en de resultaten te bestuderen. Als je mazzel hebt maak je ook nog een paar tikfouten waardoor je moet achterhalen wat er fout ging: dan leer je het meest.

4.  In sommige gevallen matcht de omgeving niet met de omgeving die jij op je computer hebt. Zorg dat je uitzoekt hoe je dan moet handelen en betrek de assistenten hierbij. Je zou elk commando in de workshop moeten kunnen uitproberen.

## Uitzoekvragen

Deze vragen helpen je nadenken over bestandssystemen.

1.  Wat is de minimale informatie die een directory over elke file moet bevatten? Waarom is dit minimaal, ofwel waarom zou het anders niet kunnen werken als opslag?

1.  Geef het absolute pad van het bestand `access.old` uit figuur 11.5 van het boek.

1.  Stel dat de "current working directory" (huidige directory) is `C:\Windows\System`. Geef het relatieve pad naar het bestand `proj3.java` zoals in figuur 11.4 van het boek.

<details markdown="1"><summary markdown="span">Antwoorden</summary>
1.  Een bestandssysteem heeft als doel de inhoud van een harddisk te beheren. Een harddisk is een rij binaire data zonder structuur. Om "files" bij te houden is minimaal nodig de naam van elke file plus de startpositie en eindpositie. Anders raken files kwijt of overschrijven ze elkaar. Alle andere informatie zoals tijd, toegangsrechten en type zijn niet essentieel in deze zin.

2.  `/etc/mail/access.old`. Dit is een UNIX-systeem dus de "root" wordt aangegeven door met een `/` (slash) te starten.

3.  `..\..\My Documents\csc101\proj3.java`. In een Windows-systeem gebruiken we `\` (backslash) om de componenten in een pad te onderscheiden. Omdat `My Documents` in de root staat moeten we vanuit `C:\Windows\System` helemaal terug met hulp van `..\..\`
</details>
