University: [ITMO University](https://itmo.ru/ru/)
Faculty: [FICT](https://fict.itmo.ru)
Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)
Year: 2022/2023
Group: K4110c
Author: German Ilya Andreevich
Lab: Lab4
Date of create: 03.12.2022
Date of finished: 
1. При запуске minikube устанавливаем плагин CNI=calico и режим работы Multi-Node Clusters одновеременно, разворачиваем 2 ноды
![image](https://user-images.githubusercontent.com/116584865/208431995-3b975a46-8b1d-49a4-b879-34e6e9d95ffe.png)
2. Проверяем работу CNI плагина Calico и количество нод
![image](https://user-images.githubusercontent.com/116584865/208436313-70f04dec-462f-4d2d-b3df-ed9c92db25e9.png)
![image](https://user-images.githubusercontent.com/116584865/208436620-500e1470-4b67-49ae-8daf-339d0fd4c21b.png)
Назначаем IP-адреса
3. Добавление labels для нод:
![image](https://user-images.githubusercontent.com/116584865/208692026-cacd8a4c-2782-4be0-a7b6-5fdbedd958fa.png)
4. Деплоим манифест для создания calico пода
![image](https://user-images.githubusercontent.com/116584865/208743184-78aeb6f1-ea47-4cde-8f6b-2c0e804a78db.png)
5. Деплоим манифест написанный для IP-пулов
![image](https://user-images.githubusercontent.com/116584865/208745434-0718bccd-fb69-4e08-8891-11a2077144fe.png)
Проверяем результат, деплоим манифесты для конфига, сервиса и репликасет
![image](https://user-images.githubusercontent.com/116584865/208886733-17ab1088-bc7e-4547-91f1-67c24747a3e3.png)
6. Проверяем, понимаем что образ контейнера не ложится на наши поды
![image](https://user-images.githubusercontent.com/116584865/208899584-e35c1338-8463-4837-8185-3809829fc0b0.png)


