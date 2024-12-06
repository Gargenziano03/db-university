# GROUP BY 
## Contare quanti iscritti ci sono stati ogni anno
```sql
SELECT COUNT(id) as `students`, `enrolment_date`
FROM `students` 
GROUP BY `enrolment_date`; 
```

## Contare gli insegnanti che hanno l'ufficio nello stesso edificio

```sql
 SELECT COUNT(id) as `teachers`, `office_address`
FROM `teachers` 
GROUP BY `office_address`;
 ```

## Calcolare la media dei voti di ogni appello d'esame

```sql
SELECT `exam_id`, AVG(`vote`) AS `average_vote`
FROM `exam_student`
GROUP BY `exam_id`;
 ```

# Contare quanti corsi di laurea ci sono per ogni dipartimento

```sql
SELECT COUNT(`degrees`.`id`) AS `degree_count`,
`departments`.`name`
FROM `departments`
JOIN `degrees`
ON `departments`.`id` = `degrees`.`department_id`
GROUP BY `departments`.`id`, `departments`.`name`;
```


## JOIN

# Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

```sql
SELECT `students`.*,
`degrees`.`name` AS `degree_name`
FROM `students`
JOIN `degrees`
ON `students`.`degree_id` = `degrees`.`id`
WHERE `degrees`.`name` = 'Corso di Laurea in Economia';
```

# Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze

```sql
SELECT `degrees`.*,
`departments`.`name` AS `department_name`
FROM `departments`
JOIN `degrees`
ON `degrees`.`department_id` = `departments`.`id`
WHERE `departments`.`name` = 'Dipartimento di Neuroscienze'
AND `degrees`.`level` = 'magistrale';
```

# Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

```sql
SELECT `courses`.`name`,
`teachers`.`id`,
`teachers`.`name` AS `teacher_name`,
`teachers`.`surname` AS `teacher_surname`
FROM `teachers`
JOIN `course_teacher` ON `course_teacher`.`teacher_id` = `teachers`.`id` 
JOIN `courses` ON `course_teacher`.`course_id` = `courses`.`id` 
WHERE `teachers`.`id` = 44;
```

# Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome

```sql
SELECT `students`.*,
`departments`.`name` AS `department_name`,
`degrees`.`name` AS `degree_name`
FROM `students`
JOIN `degrees` ON `students`.`degree_id` = `degrees`.`id`
JOIN `departments` ON `degrees`.`department_id` = `departments`.`id`
ORDER BY `students`.`surname`, `students`.`name` ASC;
```

# Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti
```sql
SELECT `degrees`.`name` AS `degrees_name`,
`courses`.`name` AS `courses_name`,
`teachers`.`name` AS `teachers_name`,
`teachers`.`surname` AS `teachers_surname`
FROM `degrees` 
JOIN `courses` ON `courses`.`degree_id` = `degrees`.`id`
JOIN `course_teacher` ON `course_teacher`.`course_id` = `courses`.`id`
JOIN `teachers` ON `teachers`.`id` = `course_teacher`.`teacher_id`;
```

# Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)

```sql
SELECT DISTINCT `teachers`.*
FROM `teachers`
JOIN `course_teacher` ON `course_teacher`.`teacher_id` = `teachers`.`id` 
JOIN `courses` ON `course_teacher`.`course_id` = `courses`.`id`
JOIN `degrees` ON `courses`.`degree_id` = `degrees`.`id`
JOIN `departments` ON `degrees`.`department_id` = `departments`.`id`;
```