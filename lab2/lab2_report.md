University: [ITMO University](https://itmo.ru/ru/)
Faculty: [FICT](https://fict.itmo.ru)
Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)
Year: 2022/2023
Group: K4110c
Author: German Ilya Andreevich
Lab: Lab2
Date of create: 03.12.2022
Date of finished: 

1. Скачиваем образ контейнера "ifilyaninitmo/itdt-contained-frontend:master"
![image](https://user-images.githubusercontent.com/116584865/205890505-8ffd366e-22b2-4d9b-8acd-dfe1333c1719.png)
2. Создаём deployment по образу выше и 2 реплики к нему
 ![image](https://user-images.githubusercontent.com/116584865/205901750-145de126-dd45-4b21-978a-3c8e9be7dacb.png)
 ![image](https://user-images.githubusercontent.com/116584865/205902281-8a7e57e8-b6ea-4a28-8be0-5d437df5d540.png)
 Пересоздаём деплой декларативным подходом и так же создаем сервис loadbalancer
![image](https://user-images.githubusercontent.com/116584865/205957109-b54f4ace-829f-464b-802b-8b7d7df0c1cd.png)
![image](https://user-images.githubusercontent.com/116584865/205957375-24532f09-4e61-4ab4-a612-83ba36c20d4f.png)
После множества попыток, поды находятся в состоянии ImagePullBackOff и не собираются работать. Вроде как проблема с образом.
![image](https://user-images.githubusercontent.com/116584865/206164288-f6f9fc0b-62c5-41fe-af7a-decd83223524.png)



