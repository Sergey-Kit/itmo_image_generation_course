![image](https://github.com/Sergey-Kit/itmo_image_generation_course/assets/82327055/62a42e14-b2d5-4bc5-b18c-e1822925cf69)# Обработка и генерация изображений

Репозиторий Китаева Сергея

## Задача 

### ДЗ 3. Sampling в латентном пространстве StyleGAN

Ссылка на Kaggle-ноутбук: 
[https://www.kaggle.com/code/sergeykit/dcgan](https://www.kaggle.com/code/sergeykit/stylegan-hw)

#### Найдены проекции изображений в пространстве StyleGAN: 

 - с помощью среднего вектора латентного пространства (1)
     
 - с помощью лосса между выходами энкодера (2)

![image](https://github.com/Sergey-Kit/itmo_image_generation_course/assets/82327055/ee27778f-6a26-4b0a-a398-c69ee31cd862)

Исходные изображения | (1) | (2)

Оптимальные гиперпараметры:

  w_avg_samples = 10000
  
  regularize_noise_weight = 5e5
  
  rec_weight = 0.5
  
  lpips_weight = 1


#### Style transfer

Исходный стиль и его отображение в латентном пространстве:

Из вектора W+ брал последние индексы (интервал(9, 18), первые индексы сильно меняют атрибуты и форму лица

![image](https://github.com/Sergey-Kit/itmo_image_generation_course/assets/82327055/057a675b-52ba-4c45-8759-367743a77c06)

Трансфер стиля:

![image](https://github.com/Sergey-Kit/itmo_image_generation_course/assets/82327055/656a49d1-b78b-4370-96d5-31f7613204e9)

Исходный стиль и его отображение в латентном пространстве:

![image](https://github.com/Sergey-Kit/itmo_image_generation_course/assets/82327055/3ac44f09-10d4-4d2b-b833-bbe8e80b41c8)

Трансфер стиля:

![image](https://github.com/Sergey-Kit/itmo_image_generation_course/assets/82327055/2faaf633-7873-4115-bedb-d58f12f0cca8)

Исходный стиль и его отображение в латентном пространстве:

![image](https://github.com/Sergey-Kit/itmo_image_generation_course/assets/82327055/0342d2c1-68eb-4ec7-8380-a58ecb365802)

Трансфер стиля:

![image](https://github.com/Sergey-Kit/itmo_image_generation_course/assets/82327055/2e76765f-6651-478e-923c-20619e8f84d3)

Если взять первые индексы:

![image](https://github.com/Sergey-Kit/itmo_image_generation_course/assets/82327055/41c51285-40ae-4c55-96a5-2fa64e147664)

### Expression Transfer

Улыбка - индексы - интервал от 0 до 5

![image](https://github.com/Sergey-Kit/itmo_image_generation_course/assets/82327055/bc73a740-99cf-46fc-8b09-cd133e779ec5)

Возраст - индексы - интервал от 0 до 9

![image](https://github.com/Sergey-Kit/itmo_image_generation_course/assets/82327055/9efbe55c-4c43-4c67-9189-3580db53de4b)

Поворот головы - индексы -  от 0 до 6

![image](https://github.com/Sergey-Kit/itmo_image_generation_course/assets/82327055/094d6029-2a06-44cd-8105-fb878b880b4e)


