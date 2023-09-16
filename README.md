# Домашнее задание к занятию "Очереди RabbitMQ" - `Умаров Азиз`


## Задание 1. Установка RabbitMQ
Используя Vagrant или VirtualBox, создайте виртуальную машину и установите RabbitMQ. Добавьте management plug-in и зайдите в веб-интерфейс.

Итогом выполнения домашнего задания будет приложенный скриншот веб-интерфейса RabbitMQ.
![image](https://github.com/UmarovAM/sys-homework/assets/118117183/2486314b-c73e-4fef-acdc-e9e771cb9f9f)


## Задание 2. Отправка и получение сообщений
Используя приложенные скрипты, проведите тестовую отправку и получение сообщения. Для отправки сообщений необходимо запустить скрипт producer.py.

Для работы скриптов вам необходимо установить Python версии 3 и библиотеку Pika. Также в скриптах нужно указать IP-адрес машины, на которой запущен RabbitMQ, заменив localhost на нужный IP.

$ pip install pika
Зайдите в веб-интерфейс, найдите очередь под названием hello и сделайте скриншот. После чего запустите второй скрипт consumer.py и сделайте скриншот результата выполнения скрипта

В качестве решения домашнего задания приложите оба скриншота, сделанных на этапе выполнения.
![image](https://github.com/UmarovAM/sys-homework/assets/118117183/398e1b4e-79a1-47b0-883e-9bbf29bc31a2)

![image](https://github.com/UmarovAM/sys-homework/assets/118117183/2c5b8d3c-9b39-4ccc-8a7b-2a3e42be19c8)

![image](https://github.com/UmarovAM/sys-homework/assets/118117183/4db7473d-481c-4481-9752-1060694bd6ac)

![image](https://github.com/UmarovAM/sys-homework/assets/118117183/4b8c65c0-2270-4a83-86f8-c68b8f8252d2)

![image](https://github.com/UmarovAM/sys-homework/assets/118117183/df1234eb-ad0b-435e-906f-6284b3dd3878)

![image](https://github.com/UmarovAM/sys-homework/assets/118117183/f5126f15-47b9-463b-a886-98989e6b932c)

Для закрепления материала можете попробовать модифицировать скрипты, чтобы поменять название очереди и отправляемое сообщение.

## Задание 3. Подготовка HA кластера
Используя Vagrant или VirtualBox, создайте вторую виртуальную машину и установите RabbitMQ. Добавьте в файл hosts название и IP-адрес каждой машины, чтобы машины могли видеть друг друга по имени.

Пример содержимого hosts файла:

$ cat /etc/hosts
192.168.0.10 rmq01
192.168.0.11 rmq02
После этого ваши машины могут пинговаться по имени.

Затем объедините две машины в кластер и создайте политику ha-all на все очереди.

В качестве решения домашнего задания приложите скриншоты из веб-интерфейса с информацией о доступных нодах в кластере и включённой политикой.

Также приложите вывод команды с двух нод:

$ rabbitmqctl cluster_status
Для закрепления материала снова запустите скрипт producer.py и приложите скриншот выполнения команды на каждой из нод:
![image](https://github.com/UmarovAM/sys-homework/assets/118117183/b7df6c16-0759-4fa5-9038-f8abc8a906e8)

![image](https://github.com/UmarovAM/sys-homework/assets/118117183/e9de3532-a7cb-4ed6-96c9-7f922890e27f)

![image](https://github.com/UmarovAM/sys-homework/assets/118117183/5628ba4e-558a-4931-ae15-bd761405700d)


$ rabbitmqadmin get queue='hello'
После чего попробуйте отключить одну из нод, желательно ту, к которой подключались из скрипта, затем поправьте параметры подключения в скрипте consumer.py на вторую ноду и запустите его.

Приложите скриншот результата работы второго скрипта.

![image](https://github.com/UmarovAM/sys-homework/assets/118117183/a3b67d43-b00b-44a9-997c-e13b1e55297d)

![image](https://github.com/UmarovAM/sys-homework/assets/118117183/800f08b1-48b0-481c-a54a-0f9c87fb7ac7)

![image](https://github.com/UmarovAM/sys-homework/assets/118117183/b1291ef5-ac80-48c0-95a5-6a3821796289)

