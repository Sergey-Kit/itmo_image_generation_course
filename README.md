# Обработка и генерация изображений

Репозиторий Китаева Сергея

## Задача 

### ДЗ 4. Обучение Stable diffusion 1.5 методом Dreambooth

Собран датасет и обучен U-Net.

Параметры
--instance_prompt="a photo of sks woman face" токен на который мы хотим обучить персонажа

--class_prompt="a photo of woman face" промт для регуляризации

![Снимок экрана 2024-04-22 012546](https://github.com/Sergey-Kit/itmo_image_generation_course/assets/82327055/b3c075da-09c5-47ee-9fc2-d2fba20b0e42)
![Снимок экрана 2024-04-22 012524](https://github.com/Sergey-Kit/itmo_image_generation_course/assets/82327055/5e1e2bdb-9a16-4904-9f52-62b1e21e3625)
![Снимок экрана 2024-04-22 012501](https://github.com/Sergey-Kit/itmo_image_generation_course/assets/82327055/0bcfe600-b5ca-43cc-8043-f8cd09473ea6)
![Снимок экрана 2024-04-22 012441](https://github.com/Sergey-Kit/itmo_image_generation_course/assets/82327055/eeeedfa6-4656-4c27-bf61-9933e720ef8e)
![Снимок экрана 2024-04-22 012353](https://github.com/Sergey-Kit/itmo_image_generation_course/assets/82327055/d6629fcc-7eb3-40da-bea7-599d4555fca9)



#### Обучена LoRA и проведены эксперименты: 

пример - rank 4 lr 8e-5

![Снимок экрана 2024-04-22 013528](https://github.com/Sergey-Kit/itmo_image_generation_course/assets/82327055/7f4e390d-6331-495d-a5e9-541f15953803)
![Снимок экрана 2024-04-22 012546](https://github.com/Sergey-Kit/itmo_image_generation_course/assets/82327055/53fc82c0-b533-48ea-bc75-6f830b22056f)
![Снимок экрана 2024-04-22 012524](https://github.com/Sergey-Kit/itmo_image_generation_course/assets/82327055/f4d41787-bf93-4c3d-b6d5-0f85b9bcf897)
![Снимок экрана 2024-04-22 012501](https://github.com/Sergey-Kit/itmo_image_generation_course/assets/82327055/533de96d-11fc-4b9f-a1e4-7e9175200fed)
![Снимок экрана 2024-04-22 012441](https://github.com/Sergey-Kit/itmo_image_generation_course/assets/82327055/6160f84d-2cee-4bd6-993d-47c0cb481adf)


#### Сравнить лучший чекпоинт Unet и Lora


#### ControlNet




Возраст - индексы - интервал от 0 до 9



Поворот головы - индексы -  от 0 до 6

