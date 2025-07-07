Modellizzare la struttura di un database per memorizzare tutti i dati riguardanti una università:
sono presenti diversi Dipartimenti (es.: Lettere e Filosofia, Matematica, Ingegneria ecc.);
ogni Dipartimento offre più Corsi di Laurea (es.: Civiltà e Letterature Classiche, Informatica, Ingegneria Elettronica ecc..)
ogni Corso di Laurea prevede diversi Corsi (es.: Letteratura Latina, Sistemi Operativi 1, Analisi Matematica 2 ecc.);
ogni Corso può essere tenuto da diversi Insegnanti;
ogni Corso prevede più appelli d'Esame;
ogni Studente è iscritto ad un solo Corso di Laurea;
ogni Studente può iscriversi a più appelli di Esame;
per ogni appello d'Esame a cui lo Studente ha partecipato, è necessario memorizzare il voto ottenuto, anche se non sufficiente.
Pensiamo a quali entità (tabelle) creare per il nostro database e cerchiamo poi di stabilirne le relazioni. Infine, andiamo a definire le colonne e i tipi di dato di ogni tabella.

Table Name: University db

# Entities

- departments
- courses
- teachers
- students
- exams
- subject

## department

- id | BIGINT NOT NULL AUTO INCREMENT
- dp_name | VARCHAR(50) NOT NULL
- dp_address | VARCHAR(50) NOT NULL

## course

- id BIGINT NOT NULL AUTO INCREMENT
- subject_id | VARCHAR(30) NOT NULL

## teacher

- id BIGINT NOT NULL AUTO INCREMENT
- name | VARCHAR(20) NOT NULL
- last_name | VARCHAR(20) NOT NULL
- eMail | VARCHAR(50) NULL
- teached_subject | VARCHAR(30) NOT NULL

## student

- id BIGINT NOT NULL AUTO INCREMENT
- name | VARCHAR(30) NOT NULL
- last_name | VARCHAR(30) NOT NULL
- eMail | VARCHAR(50) NULL

## exan

- id BIGINT NOT NULL AUTO INCREMENT
- subject_id | VARCHAR(50) NOT NULL
- student_id | VARCHAR(50) NULL
- date | DATE NOT NULL
- result | VARCHAR(10) NOT NULL

## subject

- id BIGINT NOT NULL AUTO INCREMENT
- type | VARCHAR(50) NOT NULL
- class_days | DATE NOT NULL
