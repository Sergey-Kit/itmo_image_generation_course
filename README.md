# Обработка и генерация изображений

Репозиторий Китаева Сергея

## Задача 

Задача - бинарная сегментация опухолей на МРТ головного мозга https://www.kaggle.com/datasets/mateuszbuda/lgg-mri-segmentation

Цель эксперимента: сравнить две архитектуры (Feature Pyramid Network и UNet на основе предобученной ResNext50), посмотреть, как быстро и насколько качественно будут достигаться метрики (DICE) по прошествии 10 эпох

## FPN:

![image](https://github.com/Sergey-Kit/itmo_image_generation_course/assets/82327055/3b90e2ed-a5d3-49cb-ba2e-83e0afb01a63)

Итоговые значения метрик:
Mean loss on train: 0.36476130218341435 
Mean DICE on train: 0.6812218097143663 
Mean DICE on validation: 0.7494544150043855

## Unet with ResNeXt50 backbone:

![image](https://github.com/Sergey-Kit/itmo_image_generation_course/assets/82327055/eda2b563-ca92-4312-8663-02f930cb12a9)

Итоговые значения метрик:
Mean loss on train: 0.1637195113018669 
Mean DICE on train: 0.8546868684663235 
Mean DICE on validation: 0.9226899728291537

![image](https://github.com/Sergey-Kit/itmo_image_generation_course/assets/82327055/ec069a9b-d677-466c-b8fe-5551e24b6dbc)

## Выводы по результатам проведенного эксперимента

Целью было сравнить скорость достижения метрик и сами метрики. 
Обучение производилось на GPU P100 16GB/ Модель Unet обучалась 4 минуты 24 секунды, FPN обучалась 3 минуты 25 секунд, а Unet with ResNeXt50 backbone - 11 минут 50 секунд.

Выводы: Более тяжеловесная модель ResNeXt50 сильно превосходит по качеству модель FPN, однако уступает в скорости обучения.
