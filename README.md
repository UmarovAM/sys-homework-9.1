# Домашнее задание к занятию "Репликация и масштабирование. Часть 1" - `Умаров Азиз`



### Задание 1

На лекции рассматривались режимы репликации master-slave, master-master, опишите их различия.

*Ответить в свободной форме.*

---

### Задание 2

Выполните конфигурацию master-slave репликации, примером можно пользоваться из лекции.

*Приложите скриншоты конфигурации, выполнения работы: состояния и режимы работы серверов.*
```mysql
STOP SLAVE;
CHANGE MASTER TO MASTER_HOST='192.168.31.124', MASTER_USER='replication1', MASTER_PASSWORD='14zozegiM$', MASTER_LOG_FILE='mysql-bin.000223', MASTER_LOG_POS=1109;
START SLAVE;
SHOW SLAVE STATUS\G
```
![image](https://github.com/UmarovAM/sys-homework/assets/118117183/f963117a-84ce-4689-a151-97a8b024d3e7)
![image](https://github.com/UmarovAM/sys-homework/assets/118117183/a2088119-22c1-4a37-87ce-7a7c5658657a)
![image](https://github.com/UmarovAM/sys-homework/assets/118117183/cd09b986-f1d8-4c97-99ca-77e000c01e4e)

master
![image](https://github.com/UmarovAM/sys-homework/assets/118117183/962a3d70-bebc-491c-b878-b274f775d0c2)

slave
![image](https://github.com/UmarovAM/sys-homework/assets/118117183/9eab7d36-538c-45b6-b45b-2ead21bbb148)

---

## Дополнительные задания (со звёздочкой*)
Эти задания дополнительные, то есть не обязательные к выполнению, и никак не повлияют на получение вами зачёта по этому домашнему заданию. Вы можете их выполнить, если хотите глубже шире разобраться в материале.

---

### Задание 3* 

Выполните конфигурацию master-master репликации. Произведите проверку.

*Приложите скриншоты конфигурации, выполнения работы: состояния и режимы работы серверов.*
