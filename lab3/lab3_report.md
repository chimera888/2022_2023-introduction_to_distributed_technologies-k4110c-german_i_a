University: [ITMO University](https://itmo.ru/ru/)
Faculty: [FICT](https://fict.itmo.ru)
Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)
Year: 2022/2023
Group: K4110c
Author: German Ilya Andreevich
Lab: Lab3
Date of create: 03.12.2022
Date of finished: 
1. Создаём configMap с переменными REACT_APP_USERNAME, REACT_APP_COMPANY_NAME.
![image](https://user-images.githubusercontent.com/116584865/206217285-f955ff7c-8a4c-44a2-b9a8-b409f51a2e17.png)
2. Создаём ReplicaSet с 2-мя репликами контейнера, использованного в предыдущей лабораторной работе 
![image](https://user-images.githubusercontent.com/116584865/206219569-20f02509-e06f-4030-8dba-82c38ae6dbf9.png)
3. Создаём сервис
![image](https://user-images.githubusercontent.com/116584865/206220556-e808337f-f032-42dc-98d6-efedf6aacc7f.png)
4. Подключаем ingress 
![image](https://user-images.githubusercontent.com/116584865/206226499-c445a1c4-af7e-4832-9ee1-4503a51edbd9.png)
5. При помощи утилиты mkcert генерируем сертификат и ключ к нему
![image](https://user-images.githubusercontent.com/116584865/206274541-818247e1-1687-4366-ac3b-ca1668fc5b9b.png)
6. В манифесте ingress вставляем сгенерированный host "example.com", деплоим ингресс
![image](https://user-images.githubusercontent.com/116584865/206284453-67f8c5a9-3de9-4ce6-9113-2bcf259c6503.png)
7. добавляем IP адрес ingress и FQDN, то есть 127.0.0.1, example.com в hosts файл по пути C:\Windows\System32\drivers\etc
![image](https://user-images.githubusercontent.com/116584865/206286024-412f6070-a542-4e9c-9944-c4f0731c0d8e.png)
8. Пытаемся подключиться к контейнеру
![image](https://user-images.githubusercontent.com/116584865/206290229-76f8a58b-e234-4cbf-ab11-4c23a2da9b04.png)
Получаем следующий результат:
![image](https://user-images.githubusercontent.com/116584865/206291174-3652ea5e-6113-4965-975a-4925c0142d8e.png)
9. Пробуем убрать IP address и FQDN из файла hosts
Получаем следующий результат:
![image](https://user-images.githubusercontent.com/116584865/206291348-239a8361-5310-46d1-baf7-eed962b72190.png)
Схема организации:
![image](https://user-images.githubusercontent.com/116584865/206495244-70a969db-75ad-435d-9cc7-dbce6a8974fb.png)

