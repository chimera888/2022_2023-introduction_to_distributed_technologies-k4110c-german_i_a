University: [ITMO University](https://itmo.ru/ru/)
Faculty: [FICT](https://fict.itmo.ru)
Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)
Year: 2022/2023
Group: K4110c
Author: German Ilya Andreevich
Lab: Lab2
Date of create: 03.12.2022
Date of finished: 

Попытка номер 2 спустя 2 дня мучений.
1. Пушим образ контейнера в миникуб
 ![image](https://user-images.githubusercontent.com/116584865/206180650-6ae4404d-1a32-4d94-a6a7-e48eaeff829d.png)
2. Создаём deploy с двумя репликами, манифест в репозитории
![image](https://user-images.githubusercontent.com/116584865/206180968-62ceeada-0768-4811-89cf-2d159a06dbf7.png)
3. Создаём сервис NodePort с названием service, манифест сервиса в репозитории
![image](https://user-images.githubusercontent.com/116584865/206181128-4b23da61-15bd-4991-a6c6-e737185213e3.png)
4. Пытаемся подключить к контейнеру
![image](https://user-images.githubusercontent.com/116584865/206182586-075f5dce-793b-4d75-8910-2c86415bf615.png)
Через port-forward не получается. Очень долго пытался разобраться, почему- не получилось. Пробуем через service
![image](https://user-images.githubusercontent.com/116584865/206182961-24c5f950-00f7-41d9-8d85-891c4be89684.png)
Пробуем создать сервис через терминал и прокинуть порт компьютера в контейнер
![image](https://user-images.githubusercontent.com/116584865/206183710-2b19695f-df1f-4d34-a7cd-81b1a9af95b3.png)
Получаем результат:
![image](https://user-images.githubusercontent.com/116584865/206183792-17f6464c-aba6-477e-bc3a-6fcf5dfe8fff.png)
Поскольку доступ к контейнеру я получил локально, то при обновлении имя контейнера не меняется, как, на мой взгляд, произошло бы в случае подключения через сервис, написанный декларативным методом. В таком случае сервис распределял бы запрос между двумя нодами, и имя контейнера менялось бы на имя второй реплики.
Проверяем логи
![image](https://user-images.githubusercontent.com/116584865/206187349-9d883e58-8888-4c7a-bc7a-08d5f0bce546.png)


