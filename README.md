# Домашнее задание к занятию "SQL. Часть 1" - `Умаров Азиз`


### Задание 1

Получите уникальные названия районов из таблицы с адресами, которые начинаются на “K” и заканчиваются на “a” и не содержат пробелов.

`
SELECT DISTINCT district
FROM address
WHERE district LIKE 'K%a' AND district NOT LIKE '% %';
`
![image](https://github.com/UmarovAM/sys-homework/assets/118117183/5ec011a0-8c00-45fd-9278-cbef2499303d)


### Задание 2

`
select amount, payment_date
from payment
where amount > 10 and cast(payment_date as date) between 20050616 and 20050618
order by payment_date;
`

Получите из таблицы платежей за прокат фильмов информацию по платежам, которые выполнялись в промежуток с 15 июня 2005 года по 18 июня 2005 года **включительно** и стоимость которых превышает 10.00.

![image](https://github.com/UmarovAM/sys-homework/assets/118117183/cdf7133a-0cb2-40e2-8003-0c0982d16460)


### Задание 3

Получите последние пять аренд фильмов.

![image](https://github.com/UmarovAM/sys-homework/assets/118117183/315a30f7-a8f0-49f5-9fc0-fbbf96506b6d)


### Задание 4

Одним запросом получите активных покупателей, имена которых Kelly или Willie. 

Сформируйте вывод в результат таким образом:
- все буквы в фамилии и имени из верхнего регистра переведите в нижний регистр,
- замените буквы 'll' в именах на 'pp'.

![image](https://github.com/UmarovAM/sys-homework/assets/118117183/54708bb9-e002-404e-aaa6-2f176c071c26)


## Дополнительные задания (со звёздочкой*)
Эти задания дополнительные, то есть не обязательные к выполнению, и никак не повлияют на получение вами зачёта по этому домашнему заданию. Вы можете их выполнить, если хотите глубже шире разобраться в материале.

### Задание 5*

Выведите Email каждого покупателя, разделив значение Email на две отдельных колонки: в первой колонке должно быть значение, указанное до @, во второй — значение, указанное после @.

### Задание 6*

Доработайте запрос из предыдущего задания, скорректируйте значения в новых колонках: первая буква должна быть заглавной, остальные — строчными.
