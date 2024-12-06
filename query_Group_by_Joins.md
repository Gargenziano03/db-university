# GROUP BY 

## Contare quanti iscritti ci sono stati ogni anno
```SELECT COUNT(id) as `students`, `enrolment_date`
FROM `students` 
GROUP BY `enrolment_date`; ```

## Contare gli insegnanti che hanno l'ufficio nello stesso edificio

``` SELECT COUNT(id) as `teachers`, `office_address`
FROM `teachers` 
GROUP BY `office_address`; ```

## Calcolare la media dei voti di ogni appello d'esame

```SELECT `exam_id`, AVG(`vote`) AS `average_vote`
FROM `exam_student`
GROUP BY `exam_id`; ```

# Contare quanti corsi di laurea ci sono per ogni dipartimento

```SELECT COUNT(`degrees`.`id`) AS `degree_count`,
`departments`.`name`
FROM `departments`
JOIN `degrees`
ON `departments`.`id` = `degrees`.`department_id`
GROUP BY `departments`.`id`, `departments`.`name`;```