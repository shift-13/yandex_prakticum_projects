# Отток клиентов из банка

## Описание проекта
Из «Бета-Банка» стали уходить клиенты. 
Банковские маркетологи посчитали: сохранять текущих клиентов дешевле, чем привлекать новых.
Предоставлены исторические данные о поведении клиентов и расторжении договоров с банком. 

**Цель:** Постройть модель с предельно большим значением F1-меры. Измерить AUC-ROC, сравнить её значение с F1-мерой.

**Задача:** Нужно спрогнозировать, уйдёт клиент из банка в ближайшее время или нет.  

## Что было сделано
Изучены и подготовлены данные. 
Для разных моделей по разному закодированы нечисловые признаки. 
Сделано масштабирование и построено три модели: Логистическая регрессия, Дерево решений и Случайный лес. 
Оценивалось качество по метрикам ROC AUC и F1 меры. Выбрана лучшая модель и использована на тестовом наборе.  

## Вывод
Нашей задачей было построить модель, которая бы предсказывала уход клиента из банка. 
Для определения качества модели мы использовали F1 меру и ROC-кривую.
Мы отфильтровали датасет и закодировали категориальные признаки. 
Для модели логистической регрессии использовали прямое кодирование (One Hot Encoding), 
а для моделей леса и дерева использовали порядковое кодирование (Ordinal Encoding). 
Так как в данных некоторые числовые значения имели разный диапазон значений, мы масштабировали некоторые колонки. 
В данных наблюдался дисбаланс классов, поэтому использовали разные методы балансировки данных. 
При этом значения ROC кривой существенно не менялись.  

**Получили результаты:**

* *Логистическая регрессия:* на изначальных данных значение F1 = 0.32, roc_auc = 0.78. После балансировки максимальное значение F1 стало 0.53.
* *Дерево решений:* без учета баланса F1 = 0.59, roc_auc = 0.81. После использования методов балансировки значение меры F1 уменьшилось до 0.55 - 0.57.
* *Случайный лес:* результат изначальных данных - F1 = 0.57, roc_auc = 0.87. После метода downsample мера F1 = 0.644.
Модель случайного леса показала лучшие результаты, поэтому мы объединили выборки, сбалансировали и снова обучили модель. Проверили модель на тестовых данных, получили: F1 = 0.61, roc_auc = 0.85. Эти показатели говорят о том, что модель довольно хорошо предсказывает потенциальный уход клиента.