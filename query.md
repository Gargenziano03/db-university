# Selezionare tutti gli studenti nati nel 1990 (160)
```sql
SELECT `date_of_birth`
FROM `students`
WHERE year(`date_of_birth`) = 1990;
```

# Selezionare tutti i corsi che valgono più di 10 crediti (479)

```sql
SELECT `cfu`
FROM `courses`
WHERE `cfu` > 10;
```

# Selezionare tutti gli studenti che hanno più di 30 anni

```sql
SELECT `date_of_birth`
FROM `students`
WHERE year(`date_of_birth`) < 1994;
```

# Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea (286)

```sql
SELECT *
FROM `courses`
WHERE `year` = 1
AND `period` = 'I semestre';
```

# Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20/06/2020 (21)

```sql
SELECT *
FROM `exams`
WHERE hour > '14:00'
AND date = '2020-06-20';
```

# Selezionare tutti i corsi di laurea magistrale (38)

```sql
SELECT *
FROM `degrees`
WHERE `level` = 'magistrale';
```

# Quanti sono gli insegnanti che non hanno un numero di telefono? (50)


```sql
SELECT COUNT(*)
FROM `teachers`
WHERE `phone` IS NULL;
```
# Inserire nella tabella degli studenti un nuovo record con i propri dati (per il campo degree_id, inserire un valore casuale)

```sql
INSERT INTO students (degree_id, name, surname, date_of_birth, fiscal_code, enrolment_date, registration_number, email)
VALUES (1, 'Gennaro', 'argenziano', '2003-06-20', 'GTUCDC22G33B767P', '2023-12-23', '999999', 'gargenziano@email.com');
```
# Cambiare il numero dell’ufficio del professor Pietro Rizzo in 126

```sql
UPDATE teachers
SET office_number = 126
WHERE id = 56;
```
