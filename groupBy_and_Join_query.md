Group by:

1. Contare quanti iscritti ci sono stati ogni anno

select count(\*) as `number_of_enrolements`, year(`enrolment_date`) as `enrolment_year`
from `students`
group by `enrolment_year`

2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio

select count(\*) as `building_office`
from `teachers`
group by office_address

3. Calcolare la media dei voti di ogni appello d'esame

select avg(`vote`) as `votes_avarage`, `exam_id`
from `exam_student`
group by `exam_id`

4. Contare quanti corsi di laurea ci sono per ogni dipartimento

select count(\*) as `degrees_for_department`, `department_id`
from `degrees`
group by `department_id`

Join:

5. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

select \*
from `students`
join `degrees`
on `students`.`degree_id` = `degrees`.`id`
where `degrees`.`name` like "Corso di Laurea in Economia"

6. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze

select \*
from `degrees`
join `departments`
on `degrees`.`level` = `departments`.`name`
where `degrees`.`level` like "Magistrale" and `departments`.`name` like "Neuroscienze"

7. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

select \*
from `courses`
join `course_teacher`
on `courses`.`id` = `course_teacher`.`teacher_id`
where `teacher_id` = "44"

8. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome

select \*
from `students`
join `degrees`
on `students`.`degree_id` = `degrees`.`department_id`
order by `students`.`surname` asc, `students`.`name` asc

9. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

select \*
from `degrees`
join `courses`
on `courses`.`degree_id` = `degrees`.`id`
join `course_teacher`
on `course_teacher`.`course_id` = `courses`.`id`
join `teachers`
on `teachers`.`id` = `course_teacher`.`teacher_id`

10. Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)

11. BONUS: Selezionare per ogni studente il numero di tentativi sostenuti per ogni esame, stampando anche il voto massimo. Successivamente, filtrare i tentativi con voto minimo 18
