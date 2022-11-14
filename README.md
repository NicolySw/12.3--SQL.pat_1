# 12.3--SQL.pat_1

Задание можно выполнить как в любом IDE, так и в командной строке.

**Задание 1.**

Получите уникальные названия районов из таблицы с адресами, которые начинаются на “K” и заканчиваются на “a”, и не содержат пробелов.

![Безымянный](https://user-images.githubusercontent.com/100844122/201615855-24e67b3d-ccb5-446e-b42a-96866f19f50c.png)

**код запроса:**

select distinct district from address 
where district like 'k%a' and district not like  '% %'
 
**distinct** - применяется для удаления дубликатов

**where** - выборка

**like 'k%a' and district not like  '% %'** - условие начинается с k заканчивается на a (like 'k%a' ) и не содержит пробел  (not like  '% %' )




Задание 2.
Получите из таблицы платежей за прокат фильмов информацию по платежам, которые выполнялись в промежуток с 15 июня 2005 года по 18 июня 2005 года включительно, и стоимость которых превышает 10.00.

 
код запроса:
select payment_id, payment_date, amount  from payment
where payment_date between '2005-06-15' and '2005-06-18' and amount >10;
 
Задание 3.
Получите последние 5 аренд фильмов.

код запроса:
select payment_id, payment_date, amount  from payment
order by payment_date desc limit 5;
 
Задание 4.
Одним запросом получите активных покупателей, имена которых Kelly или Willie.
Сформируйте вывод в результат таким образом:
все буквы в фамилии и имени из верхнего регистра переведите в нижний регистр,
замените буквы 'll' в именах на 'pp'



код запроса:
select lower(first_name), replace(first_name, 'LL','pp') from customer
where first_name = 'Kelly' or first_name = 'Willie'


lower(first_name) - вывести строчными буквами 
replace(first_name, 'LL','pp') - заменить LL на pp



