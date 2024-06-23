# Домашнее задание к занятию "SQL. Часть 1" - Пергунов Д.В

### Задание 1
Получите уникальные названия районов из таблицы с адресами, которые начинаются на “K” и заканчиваются на “a” и не содержат пробелов.
```sql
SELECT DISTINCT district 
From sakila.address
WHERE district LIKE 'K%' and district LIKE '%a' and district not LIKE '% %';
#Условие начинается с К зачанчивается на а и не включает пробелов
```
![image](https://github.com/dimindrol/SQL.P1-pergunov/assets/103885836/d1f1d79e-8b2e-4595-837f-223b3a1111f6)


### Задание 2
Получите из таблицы платежей за прокат фильмов информацию по платежам, которые выполнялись в промежуток с 15 июня 2005 года по 18 июня 2005 года включительно и стоимость которых превышает 10.00.
```sql
SELECT amount AS COST, DATE(payment_date) AS DATE
FROM sakila.payment
WHERE amount > 10.00 
  AND DATE(payment_date) BETWEEN '2005-06-15' AND '2005-06-18';
#Условие стомость больше 10 и дата между 15 июня 2005 и 18 июня 2005 года включительно
```
![image](https://github.com/dimindrol/SQL.P1-pergunov/assets/103885836/0f221a5b-f760-4e5e-b2b1-0e8e814d4b2b)

### Задание 3  
Получите последние пять аренд фильмов.
```sql
SELECT *
FROM sakila.rental
ORDER BY rental_date DESC 
LIMIT 5;
```
![image](https://github.com/dimindrol/SQL.P1-pergunov/assets/103885836/b30149c7-9deb-409a-b7fa-3a257f2545b0)

### Задание 4
Одним запросом получите активных покупателей, имена которых Kelly или Willie.  
Сформируйте вывод в результат таким образом:  
все буквы в фамилии и имени из верхнего регистра переведите в нижний регистр,  
замените буквы 'll' в именах на 'pp'.  
```sql
SELECT REPLACE(LOWER(first_name), 'll', 'pp') AS FIRST_NAME, #Замена ll на pp только в имени, перевод в нижний регистр
LOWER(last_name) As LAST_NAME #Перевод в нижний регистр
from sakila.customer c
WHERE first_name LIKE 'Willie%' or first_name LIKE 'Kelly%'; #Поиск имен в таблице first_name
```
![image](https://github.com/dimindrol/SQL.P1-pergunov/assets/103885836/89d16ce8-3794-49b4-8348-8878f25e95b0)




