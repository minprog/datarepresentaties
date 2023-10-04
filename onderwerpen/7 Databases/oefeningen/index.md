# Oefeningen

Deze vragen zijn goede oefeningen voor het tentamen. Op het tentamen kun je ook vragen verwachten op basis van de jou al bekende Movies-database. De verwachting is dat je alle vragen op het tentamen correct beantwoordt, foutjes daargelaten. Je hebt dus parate kennis nodig van SQL en wat de verschillende clausules (JOIN, WHERE, enzovoort) doen. Als je merkt dat je deze kennis nog niet echt paraat hebt, dan kun je extra studeren met hulp van het videocollege of externe bronnen over SQL.

Je kunt onderstaande oefeningen niet inleveren en ze horen dus ook niet bij de deadline voor de Databases-module.

Onderstaande vragen zijn *grotendeels* representatief voor de vragen die je op het tentamen tegen zou kunnen komen, maar je zou ook vragen tegen kunnen komen die meer lijken op de vragen bij de [Movies-opdracht](/databases/movies). 

Wat je moet weten voor het tentamen:

- Alle SQL-onderdelen die je nodig kon hebben om Movies en Fiftyville op te lossen.
- Specifiek ook hoe JOIN's werken.


## Database

Voor de vragen gebruiken we de movies-database die je al kent. Hier is het schema:

    CREATE TABLE movies (
                        id INTEGER,
                        title TEXT NOT NULL,
                        year NUMERIC,
                        PRIMARY KEY(id)
                    );
    CREATE TABLE stars (
                    movie_id INTEGER NOT NULL,
                    person_id INTEGER NOT NULL,
                    FOREIGN KEY(movie_id) REFERENCES movies(id),
                    FOREIGN KEY(person_id) REFERENCES people(id)
                );
    CREATE TABLE directors (
                    movie_id INTEGER NOT NULL,
                    person_id INTEGER NOT NULL,
                    FOREIGN KEY(movie_id) REFERENCES movies(id),
                    FOREIGN KEY(person_id) REFERENCES people(id)
                );
    CREATE TABLE ratings (
                    movie_id INTEGER NOT NULL,
                    rating REAL NOT NULL,
                    votes INTEGER NOT NULL,
                    FOREIGN KEY(movie_id) REFERENCES movies(id)
                );
    CREATE TABLE people (
                    id INTEGER,
                    name TEXT NOT NULL,
                    birth NUMERIC,
                    PRIMARY KEY(id)
                );

## Vragen

Voor de volgende vragen moet je SQL-queries schrijven. De queries moeten precies zo specifiek zijn als wordt gevraagd, dus je mag geen shortcuts nemen op basis van jouw kennis van films en antwoorden.

Vergeet ook niet om te laten zien dat je een JOIN kunt schrijven.

1. Schrijf een SQL-query om de namen te selecteren van alle regisseurs die betrokken zijn bij de film 'The Matrix' uit 1999.

2. Schrijf een SQL-query die het aantal films selecteert die een rating hoger dan 8.5 hebben en meer dan 100 stemmen hebben ontvangen.

3. Schrijf een SQL-query om naam en de rating te selecteren van alle films waarin 'Marouane Meftah' speelt (de rating is `ratings.rating`).

4. Schrijf een SQL-query om de namen van alle mensen te selecteren, gesorteerd op geboortejaar, die speelden in een film uit het jaar 2005.
