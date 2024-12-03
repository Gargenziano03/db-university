# DB Structure
Modellare la struttura di un database per memorizzare tutti i dati riguardanti una universita':
sono presenti diversi Dipartimenti (es.: Lettere e Filosofia, Matematica, Ingegneria ecc.);
- ogni Dipartimento offre piu' Corsi di Laurea (es.: Civilta' e Letterature Classiche, Informatica, Ingegneria Elettronica ecc..)
- ogni Corso di Laurea prevede diversi Corsi (es.: Letteratura Latina, Sistemi Operativi 1, Analisi Matematica 2 ecc.);
- ogni Corso puo essere tenuto da diversi Insegnanti;
- ogni Corso prevede piu' appelli d'Esame;
- ogni Studente e' iscritto ad un solo Corso di Laurea;
- ogni Studente puo' iscriversi a piu' appelli di Esame;
per ogni appello d'Esame a cui lo Studente ha partecipato, e' necessario memorizzare il voto ottenuto, anche se non sufficiente. Pensiamo a quali entita' (tabelle) creare per il nostro database e cerchiamo poi di stabilirne le relazioni. Infine, andiamo a definire le colonne e i tipi di dato di ogni tabella.

## Table name 
- dipartimento
- corsi_laurea
- insegnanti
- appelli_esame
- studente 


## dipartimento : Table structure
- id | BIGINT - AUTO_INCREMENT - PK
- indirizzo | VARCHAR(50) - NOTNULL

## corsi_laurea : Table structure 
- id | BIGINT - AUTO_INCREMENT - PK
- dipartimento_id | BIGINT (UNISIGNED)
- indirizzo | VARCHAR(50) - NOTNULL

## insegnanti : Table structure 
- id | BIGINT - AUTO_INCREMENT - PK
- corsi_laure_id | BIGINT (UNISIGNED)
- nome | VARCHAR(20) - NOTNUALL
- cognome | VARCHAR(20) - NOTNULL
- materia | VARCHAR(20) - NOTNULL

## appelli_esame : Table structure 
- id | BIGINT - AUTO_INCREMENT - PK
- corsi_laure_id | BIGINT (UNISIGNED)
- tipologia | VARCHAR(10) - NOTNULL

## studente : Table structure 
- id | BIGINT - AUTO_INCREMENT - PK
- corsi_laure_id | BIGINT (UNISIGNED)
- appelli_esame_id | BIGINT (UNISIGNED)
- nome | VARCHAR(20) - NOTNUALL
- cognome | VARCHAR(20) - NOTNULL

