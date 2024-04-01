# Обработка и генерация изображений

Репозиторий Китаева Сергея

## Задача 

ДЗ 2. Имплементация GAN с изображениями 128x128
Датасет CelebA

Ссылка на Kaggle-ноутбук: 
https://www.kaggle.com/code/sergeykit/dcgan

Имплементирован CSPup блок

Имплементирован генератор GAN по заданной архитектурной схеме

Обучен имплементированный GAN

Проведены эксперименты с целью улучшить сходимость

Результаты:

  - замена BCELoss на BCEWithLogitsLoss
    ![output2](https://github.com/Sergey-Kit/itmo_image_generation_course/assets/82327055/35fb08c8-636d-4b2d-a674-5c2e92e42bdb)

  - обучение дискриминатора не на каждой итерации
    ![output3](https://github.com/Sergey-Kit/itmo_image_generation_course/assets/82327055/0855ae04-6206-4075-adff-7ef157ab695f)

  - уменьшение количества сверток в дискриминаторе
    ![output4](https://github.com/Sergey-Kit/itmo_image_generation_course/assets/82327055/313a9f7e-8bb3-44cc-93fa-0c41f0a1c5d9)

  - замена в CSPup ReLU на LeakyReLU
    ![output5](https://github.com/Sergey-Kit/itmo_image_generation_course/assets/82327055/51cfa3b0-79a2-4e82-8605-0649b7813f14)

  - изменение batch size
    ![output6](https://github.com/Sergey-Kit/itmo_image_generation_course/assets/82327055/270285d6-ee5c-4b79-b119-09bccfd050de)


![Result](https://github.com/Sergey-Kit/itmo_image_generation_course/assets/82327055/a2ef4f75-1d1c-4e41-853b-f58e7067481a)


## Исправления

имплементация CSPup блока

```
class CSPup(nn.Module):
    def __init__(self, in_channels, out_channels, kernel_size=4, stride=2, padding=1):
        super().__init__()
        self.kernel_size =kernel_size
        self.stride = stride
        self.padding = padding
        self.in_channels = in_channels
        self.out_channels = out_channels
        self.split_channels = self.in_channels//2
        self.left = nn.Sequential(
            nn.ConvTranspose2d(self.split_channels, self.out_channels, self.kernel_size, self.stride, self.padding, bias=False),
        )
        self.right = nn.Sequential(
            nn.Conv2d(self.split_channels, self.out_channels , 1, 1, 0),
            nn.ReLU(),
            nn.ConvTranspose2d(self.out_channels, self.out_channels , self.kernel_size, self.stride, self.padding, bias=False),
            nn.Conv2d(self.out_channels, self.out_channels , 3, 1, 0),
            nn.ReLU(),
            nn.Conv2d(self.out_channels, self.out_channels, 3, 1, 0),
        )
    def forward(self, x):
        x1, x2 = x.chunk(2, dim=1)
        y = self.left(x1)+self.right(x2)
        return y
```


    
