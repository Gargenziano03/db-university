# GROUP BY 

## Contare quanti iscritti ci sono stati ogni anno
```SELECT COUNT(id) as `numero_iscritti`, `enrolment_date`
FROM `students` 
WHERE `enrolment_date`
GROUP BY `enrolment_date`
```