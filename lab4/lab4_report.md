University: [ITMO University](https://itmo.ru/ru/)
Faculty: [FICT](https://fict.itmo.ru)
Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)
Year: 2022/2023
Group: K4110c
Author: German Ilya Andreevich
Lab: Lab4
Date of create: 03.12.2022
Date of finished: 
## Ход работы
1. Устанавливаем плагин Calico.
- Прежде чем запустить minikube, устанавливаем плагин `CNI=Calico`, команда `minikube start --network-plugin=cni --cni=calico` позволяет создать single-node minikube cluster, нам же нужно 2 ноды. Чтобы их создать, потребуется команда `minikube start --nodes 2 -p multinode-demo`. Теперь объединяем их в одно
- `minikube start --driver=docker -p multinode-cluster --network-plugin=cni --cni=calico --nodes 2 --kubernetes-version=v1.24.0`
- Проверяем количество созданных нод при помощи команды `kubectl get nodes`:
![image](https://user-images.githubusercontent.com/116584865/209129524-fef79199-5999-4c30-bd99-228b21372c80.png)
 - Проверяем работу CNI плагина Calico:
 - При помощи команды `kubectl get po -n kube-system -l=k8s-app=calico-node` видим созданные поды с меткой calico-node
 ![image](https://user-images.githubusercontent.com/116584865/209135309-bc77d3ab-2fe8-4c99-8775-abe340469e9a.png)
 - Для проверки работы Calico мы попробуем одну из функций под названием `IPAM Plugin`
 - Для проверки режима IPAM для запущеных ранее нод указываем label по признаку стойки или географического расположения
 Соглавно инструкции по назначению ip-адресов удаляем дефолтный ippool, убеждаемся что никаких айпи-пулов не осталось:
 ![image](https://user-images.githubusercontent.com/116584865/209140984-c6cde9c0-df5e-4cdb-9ada-593e9470810f.png)
- Для ранее запущенных нод добавляем labels:
![image](https://user-images.githubusercontent.com/116584865/209142961-97ee54d9-d3b6-42e9-b4c2-98ac1413f98e.png)
- Создаём IP pool для каждого rack
![image](https://user-images.githubusercontent.com/116584865/209145027-3a4e4e60-5dcd-48f8-b8e6-7db02886c32b.png)
- Чтобы взаимодействовать с calico, скачиваем его yaml образ с офф.сайта и деплоим в миникуб
![image](https://user-images.githubusercontent.com/116584865/209146157-a56f37ac-29b7-4edd-9b87-4acdb7277dd7.png)
- Далее, взаимодействуя с calico через неймспейс kube-system, разворачиваем ip pools
![image](https://user-images.githubusercontent.com/116584865/209148975-141e4dc6-789f-4094-a309-521b6330b974.png)
# Проверка назначения IP адресов
Для проверки развернём тестоый деплоймент с двумя репликами, как в предыдущих лабах
- Создаём деплой, и сервис, при помощи команды `kubectl get po -o wide` проверяем поды
![image](https://user-images.githubusercontent.com/116584865/209151512-e3da4313-8a96-4230-b8f1-97bb146af7df.png)
Видим проблему, образ не ложится на контейнеры, и эта проблема не решается пуллом образа в докер, до того как задеплоить манифест с calico они были в состоянии `ready`.




