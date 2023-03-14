# Заказы такси  

## Описание проекта  
Компания «Чётенькое такси» собрала исторические данные о заказах такси в аэропортах. 
Чтобы привлекать больше водителей в период пиковой нагрузки, нужно спрогнозировать количество заказов такси на следующий час.  

**Описание данных:** Количество заказов находится в столбце `num_orders`.

## Было сделано  
Сделано ресемплирование, изучены линия тренда и сезонность. Добавлены признаки. 
Построены модели, построены графики реальных значений и предсказаний. Оценка качества модели метрикой `RMSE`.

## Вывод  
Нашей задачей было предсказать количество заказов такси на ближайший час, основываясь на имеющихся данных.  
Для этого мы сделали ресемплирование данных по часам. Изучили спрос на такси по дням. 
Рассмотрели линию тренда - спрос растет в августе.  
Для обучения модели добавили признаки в данные. Разделили на обучающую и тестовую выборку в отношении 9:1.   
Для проверки качества модели использовали метрику `RMSE`.
Обучили три модели - дерево решений, линейную регрессию и `LGBMRegressor`. 
Лучшее качество показала `LGBMR`, проверили ее работу на тестовой выборки и получили качество 44.47, 
что удовлетворяет требованиям.
Однако по графикам видно, что модели предсказывают количество заказов ниже, чем было на самом деле.