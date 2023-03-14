# Страховая компания  
## Описание проекта  
Нам нужно защитить данные клиентов страховой компании «Хоть потоп». Мы разработаем такой метод преобразования данных, чтобы по ним было сложно восстановить персональную информацию.
Нужно защитить данные, чтобы при преобразовании качество моделей машинного обучения не ухудшилось.  


**Описание данных:**
* **Признаки:** пол, возраст и зарплата застрахованного, количество членов его семьи.
* **Целевой признак:** количество страховых выплат клиенту за последние 5 лет.  


## Было сделано  
Изучены данные, проверены признаки на мультиколлинеарность. Приведено математическое обоснование почему модель не ухудшится, если 
исходные данные умножить на обратимую матрицу. Составлен алгоритм преобразования. Создан `class LinearRegression`, проверена метрика качества модели
на исходных данных и преобразованных.


## Выводы  
Нашей задачей было защитить данные клиентов и при этом, чтобы качество модели не ухудшилось. Для этого было решено умножить исходные данные на случайную обратимую матрицу. В качестве метрики выбрана R2. Алгебраически доказали с помощью свойств матриц, что качество модели не изменится.
Использовали класс LinearRegression, где явно прописаны формулы построения модели обучения. Обучили модель на исходных данных и на преобразованных. Сравнили показатели метрики, она не изменилась и равна 0.44, что довольно хорошо.
В итоге имеем таблицу, где данные представлены числами и информация о клиентах защищена.