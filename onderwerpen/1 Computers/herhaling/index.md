# Oefeningen: werken met bestanden en mappen

## Niveau 1: basiscommando's

1. **Waar ben ik?**  
   - Open een terminal en controleer je huidige locatie met een commando.
   - Navigeer naar je home-map als je daar nog niet bent.

2. **Bestanden en mappen weergeven**  
   - Gebruik een commando om alle bestanden en mappen in je huidige locatie weer te geven.
   - Probeer ook verborgen bestanden weer te geven.

3. **Maak een map**  
   - Maak een nieuwe map genaamd `mijn_project`.
   - Ga de `mijn_project` map in en controleer of je erin zit.

## Niveau 2: bestanden en mappen beheren

4. **Maak en verplaats bestanden**  
   - Maak binnen `mijn_project` een leeg bestand genaamd `notities.txt`.
   - Gebruik een teksteditor om de regel `Mijn eerste projectnotities` toe te voegen aan `notities.txt`.

5. **Kopiëren en hernoemen**  
   - Kopieer `notities.txt` naar een nieuw bestand genaamd `backup_notities.txt`.
   - Hernoem `backup_notities.txt` naar `notities_backup.txt`.

6. **Maak een submap en verplaats bestanden**  
   - Maak binnen `mijn_project` een nieuwe map genaamd `docs`.
   - Verplaats `notities_backup.txt` naar `docs/`.

## Niveau 3: geavanceerde bewerkingen

7. **Verwijderen van bestanden en mappen**  
   - Maak een nieuwe map genaamd `tijdelijke_bestanden` en maak daarin drie lege bestanden: `bestand1.txt`, `bestand2.txt` en `bestand3.txt`.
   - Verwijder `bestand2.txt`.
   - Verwijder de hele map `tijdelijke_bestanden` (wees voorzichtig!).

8. **Een project organiseren**  
   - Maak binnen `mijn_project` de volgende mappenstructuur:

         mijn_project/
         ├── docs/
         │   ├── notities_backup.txt
         ├── src/
         ├── tests/

   - Verplaats `notities.txt` naar de `docs/` map.
   - Maak een nieuw leeg bestand in `src/` genaamd `main.py`.

9. **Script-automatisering**  
   - Schrijf een eenvoudig shellscript (een tekstbestand met UNIX-commando's erin) dat:
     - Een map genaamd `nieuw_project` maakt.
     - Naar `nieuw_project` navigeert.
     - Drie submappen maakt: `code/`, `data/` en `resultaten/`.
     - Een leeg bestand `README.md` maakt in `nieuw_project`.
   - Vraag je docent hoe je het script kunt uitvoeren.
   - Voer je script uit en controleer of de structuur correct is aangemaakt.
