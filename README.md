# PatikaDev-PostgreSQL

<a href='#Ödev 1'>Ödev 1</a><br>
<a href='#Ödev 2'>Ödev 2</a><br>
<a href='#Ödev 3'>Ödev 3</a><br>
<a href='#Ödev 4'>Ödev 4</a><br>
<a href='#Ödev 5'>Ödev 5</a><br>
<a href='#Ödev 6'>Ödev 6</a><br>
<a href='#Ödev 7'>Ödev 7</a><br>
<a href='#Ödev 8'>Ödev 8</a><br>
<a href='#Ödev 9'>Ödev 9</a><br>
<a href='#Ödev 10'>Ödev 10</a><br>
<a href='#Ödev 11'>Ödev 11</a><br>
<a href='#Ödev 12'>Ödev 12</a><br>

## <p id = 'Ödev 1' > Ödev 1 </p>
#### Film tablosunda bulunan title ve description sütunlarındaki verileri sıralayınız.
~~~sql
SELECT TITLE,DESCRIPTION FROM FILM;
~~~
#### Film tablosunda bulunan tüm sütunlardaki verileri film uzunluğu (length) 60 dan büyük VE 75 ten küçük olma koşullarıyla sıralayınız.
~~~sql
SELECT * FROM FILM
WHERE LENGTH >60 AND LENGTH <75
~~~
#### Film tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99 VE replacement_cost 12.99 VEYA 28.99 olma koşullarıyla sıralayınız.
~~~sql
SELECT * FROM FILM 
WHERE RENTAL_RATE=0.99 AND REPLACEMENT_COST=12.99 OR REPLACEMENT_COST=28.99
~~~
#### Customer tablosunda bulunan first_name sütunundaki değeri 'Mary' olan müşterinin last_name sütunundaki değeri nedir?
~~~sql
SELECT LAST_NAME FROM CUSTOMER 
WHERE FIRST_NAME='Mary'
~~~
#### Film tablosundaki uzunluğu(length) 50 ten büyük OLMAYIP aynı zamanda rental_rate değeri 2.99 veya 4.99 OLMAYAN verileri sıralayınız.
~~~sql
SELECT * FROM FILM
WHERE LENGTH < 50 AND (RENTAL_RATE !=2.99 OR RENTAL_RATE != 4.99)
~~~



## <p id = 'Ödev 2' > Ödev 2 </p>
#### Film tablosunda bulunan tüm sütunlardaki verileri replacement cost değeri 12.99 dan büyük eşit ve 16.99 küçük olma koşuluyla sıralayınız ( BETWEEN - AND yapısını kullanınız.)
~~~sql
SELECT TITLE,DESCRIPTION FROM FILM;
~~~
#### Actor tablosunda bulunan first_name ve last_name sütunlardaki verileri first_name 'Penelope' veya 'Nick' veya 'Ed' değerleri olması koşuluyla sıralayınız. ( IN operatörünü kullanınız.)
~~~sql
SELECT FIRST_NAME,LAST_NAME FROM ACTOR
WHERE FIRST_NAME IN ('Penelope','Nick','Ed')
~~~
#### Film tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99, 2.99, 4.99 VE replacement_cost 12.99, 15.99, 28.99 olma koşullarıyla sıralayınız. ( IN operatörünü kullanınız.)
~~~sql
SELECT * FROM FILM 
WHERE RENTAL_RATE IN (0.99,2.99,4.99) AND REPLACEMENT_COST IN (12,99,15.99,28.99)
~~~


## <p id = 'Ödev 3' > Ödev 3 </p>
#### Country tablosunda bulunan country sütunundaki ülke isimlerinden 'A' karakteri ile başlayıp 'a' karakteri ile sonlananları sıralayınız.
~~~sql
SELECT COUNTRY FROM COUNTRY
WHERE COUNTRY LIKE 'A%a'
~~~
#### country tablosunda bulunan country sütunundaki ülke isimlerinden en az 6 karakterden oluşan ve sonu 'n' karakteri ile sonlananları sıralayınız
~~~sql
SELECT COUNTRY  FROM COUNTRY
WHERE LENGTH(COUNTRY) >6 AND COUNTRY LIKE '%n'
~~~
#### Film tablosunda bulunan title sütunundaki film isimlerinden en az 4 adet büyük ya da küçük harf farketmesizin 'T' karakteri içeren film isimlerini sıralayınız.
~~~sql
SELECT TITLE FROM FILM
WHERE TITLE ILIKE ('%T%T%T%T%')
~~~
#### Film tablosunda bulunan tüm sütunlardaki verilerden title 'C' karakteri ile başlayan ve uzunluğu (length) 90 dan büyük olan ve rental_rate 2.99 olan verileri sıralayınız.

~~~sql
SELECT * FROM FILM
WHERE TITLE LIKE ('C%') AND LENGTH > 90 AND RENTAL_RATE=2.99
~~~

## <p id = 'Ödev 4' > Ödev 4 </p>
#### Film tablosunda bulunan replacement_cost sütununda bulunan birbirinden farklı değerleri sıralayınız.
~~~sql
SELECT DISTINCT(REPLACEMENT_COST) FROM FILM
~~~
#### Film tablosunda bulunan replacement_cost sütununda birbirinden farklı kaç tane veri vardır?
~~~sql
SELECT COUNT(DISTINCT((REPLACEMENT_COST))) FROM FILM
~~~
#### Film tablosunda bulunan film isimlerinde (title) kaç tanesini T karakteri ile başlar ve aynı zamanda rating 'G' ye eşittir?
~~~sql
SELECT COUNT(TITLE) FROM FILM
WHERE TITLE LIKE 'T%' AND RATING='G'
~~~
#### Country tablosunda bulunan ülke isimlerinden (country) kaç tanesi 5 karakterden oluşmaktadır?
~~~sql
SELECT COUNT(COUNTRY) FROM COUNTRY
WHERE LENGTH(COUNTRY) = 5
~~~
#### City tablosundaki şehir isimlerinin kaçtanesi 'R' veya r karakteri ile biter?
~~~sql
SELECT CITY FROM CITY
WHERE CITY ILIKE '%R'
~~~


## <p id = 'Ödev 5' > Ödev 5 </p>
#### Film tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en uzun (length) 5 filmi sıralayınız.
~~~sql
SELECT TITLE FROM FILM
WHERE TITLE LIKE '%n'
ORDER BY LENGTH DESC
LIMIT 5
~~~
#### Film tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en kısa (length) ikinci 5 filmi sıralayınız.
~~~sql
SELECT TITLE FROM FILM
WHERE TITLE LIKE '%n'
ORDER BY LENGTH 
OFFSET 5
LIMIT 5
~~~
#### Customer tablosunda bulunan last_name sütununa göre azalan yapılan sıralamada store_id 1 olmak koşuluyla ilk 4 veriyi sıralayınız.
~~~sql
SELECT * FROM CUSTOMER
WHERE STORE_ID =1
ORDER BY LAST_NAME DESC
LIMIT 4
~~~

## <p id = 'Ödev 6' > Ödev 6 </p>
#### Film tablosunda bulunan rental_rate sütunundaki değerlerin ortalaması nedir?
~~~sql
SELECT AVG(RENTAL_RATE) FROM FILM
~~~
#### Film tablosunda bulunan filmlerden kaçtanesi 'C' karekteri ile başlar?
~~~sql
SELECT COUNT(TITLE) FROM FILM
WHERE TITLE LIKE 'C%'
~~~
#### Film tablosunda bulunan filmlerden rental_rate değeri 0.99 a eşit olan en uzun (length) film kaç dakikadır?
~~~sql
SELECT MAX(LENGTH) FROM FILM
WHERE RENTAL_RATE = 0.99
~~~
#### Film tablosunda bulunan filmlerin uzunluğu 150 dakikadan büyük olanlarına ait kaç farklı replacement_cost değeri vardır?
~~~sql
SELECT COUNT(DISTINCT(REPLACEMENT_COST)) FROM FILM
WHERE LENGTH>150
~~~


## <p id = 'Ödev 7' > Ödev 7 </p>
#### Film tablosunda bulunan filmleri rating değerlerine göre gruplayınız.
~~~sql
SELECT RATING FROM FILM
GROUP BY RATING
~~~
#### Film tablosunda bulunan filmleri replacement_cost sütununa göre grupladığımızda film sayısı 50 den fazla olan replacement_cost değerini ve karşılık gelen film sayısını sıralayınız
~~~sql
SELECT REPLACEMENT_COST,COUNT(REPLACEMENT_COST) FROM FILM
GROUP BY REPLACEMENT_COST
HAVING COUNT(REPLACEMENT_COST) >50
~~~
#### Customer tablosunda bulunan store_id değerlerine karşılık gelen müşteri sayılarını nelerdir?

~~~sql
SELECT STORE_ID,COUNT(CUSTOMER_ID) FROM CUSTOMER 
GROUP BY STORE_ID
~~~
#### City tablosunda bulunan şehir verilerini country_id sütununa göre gruplandırdıktan sonra en fazla şehir sayısı barındıra country_id bilgisini ve şehir sayısını paylaşınız.
~~~sql
SELECT COUNTRY_ID,COUNT(CITY) AS NUMBER_CITY FROM CITY
GROUP BY COUNTRY_ID
~~~



## <p id = 'Ödev 8' > Ödev 8 </p>
#### Test veritabanınızda employee isimli sütun bilgileri id(INTEGER), name VARCHAR(50), birthday DATE, email VARCHAR(100) olan bir tablo oluşturalım.
~~~sql
CREATE TABLE employee 
(id int,
name varchar(50),
birthday date,
email varchar(50)
~~~
#### Oluşturduğumuz employee tablosuna 'Mockaroo' servisini kullanarak 50 adet veri ekleyelim.
~~~sql
insert into employee (id, name, birthday, email) values (1, 'Gabbie', '1978-03-10', 'gtantum0@timesonline.co.uk');
insert into employee (id, name, birthday, email) values (2, 'Gregorio', '1964-07-20', 'gscarman1@163.com');
insert into employee (id, name, birthday, email) values (3, 'Manuel', '1972-06-13', 'mbyers2@upenn.edu');
insert into employee (id, name, birthday, email) values (4, 'Amery', '1978-11-29', 'amccarthy3@shutterfly.com');
insert into employee (id, name, birthday, email) values (5, 'Viviyan', '1995-02-12', 'vmatejovsky4@storify.com');
~~~
#### Sütunların her birine göre diğer sütunları güncelleyecek 5 adet UPDATE işlemi yapalım.
~~~sql
UPDATE employee 
SET NAME= 'Tugrul',birthday= '1996-07-13' ,email= 'tugrul@gmail.com'
WHERE id=1
~~~
#### Sütunların her birine göre ilgili satırı silecek 5 adet DELETE işlemi yapalım.
~~~sql
DELETE  FROM EMPLOYEE
WHERE id=1
~~~



## <p id = 'Ödev 9' > Ödev 9 </p>
#### City tablosu ile country tablosunda bulunan şehir (city) ve ülke (country) isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.
~~~sql
SELECT CITY,COUNTRY FROM CITY
INNER JOIN COUNTRY ON CITY.COUNTRY_ID = COUNTRY.COUNTRY_ID
~~~
#### Customer tablosu ile payment tablosunda bulunan payment_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.

~~~sql
SELECT PAYMENT_ID,FIRST_NAME,LAST_NAME FROM PAYMENT
INNER JOIN CUSTOMER ON PAYMENT.CUSTOMER_ID = CUSTOMER.CUSTOMER_ID
~~~
#### Customer tablosu ile rental tablosunda bulunan rental_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.

~~~sql
SELECT RENTAL_ID,FIRST_NAME,LAST_NAME FROM CUSTOMER
INNER JOIN RENTAL ON CUSTOMER.CUSTOMER_ID = RENTAL.CUSTOMER_ID
~~~


## <p id = 'Ödev 10' > Ödev 10 </p>
#### City tablosu ile country tablosunda bulunan şehir (city) ve ülke (country) isimlerini birlikte görebileceğimiz LEFT JOIN sorgusunu yazınız.
~~~sql
SELECT CITY,COUNTRY FROM CITY
LEFT JOIN COUNTRY ON COUNTRY.COUNTRY_ID = CITY.COUNTRY_ID
~~~
#### Customer tablosu ile payment tablosunda bulunan payment_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz RIGHT JOIN sorgusunu yazınız.

~~~sql
SELECT FIRST_NAME,LAST_NAME,PAYMENT_ID FROM CUSTOMER
RIGHT JOIN PAYMENT ON CUSTOMER.CUSTOMER_ID = PAYMENT.CUSTOMER_ID
~~~
#### Customer tablosu ile rental tablosunda bulunan rental_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz FULL JOIN sorgusunu yazınız.

~~~sql
SELECT FIRST_NAME,LAST_NAME,RENTAL_ID FROM CUSTOMER
FULL JOIN RENTAL ON RENTAL.CUSTOMER_ID = CUSTOMER.CUSTOMER_ID
~~~

## <p id = 'Ödev 11' > Ödev 11 </p>
#### Actor ve customer tablolarında bulunan first_name sütunları için tüm verileri sıralayalım.
~~~sql
(SELECT FIRST_NAME FROM ACTOR)
UNION
(SELECT FIRST_NAME FROM CUSTOMER)
~~~
#### Actor ve customer tablolarında bulunan first_name sütunları için kesişen verileri sıralayalım.

~~~sql
(SELECT FIRST_NAME FROM ACTOR)
INTERSECT
(SELECT FIRST_NAME FROM CUSTOMER)
~~~
#### Actor ve customer tablolarında bulunan first_name sütunları için ilk tabloda bulunan ancak ikinci tabloda bulunmayan verileri sıralayalım.

~~~sql
(SELECT FIRST_NAME FROM ACTOR)
EXCEPT 
(SELECT FIRST_NAME FROM CUSTOMER)
~~~

#### İlk 3 sorguyu tekrar eden veriler için de yapalım.

~~~sql
(SELECT FIRST_NAME FROM ACTOR)
UNION ALL
(SELECT FIRST_NAME FROM CUSTOMER)

(SELECT FIRST_NAME FROM ACTOR)
INTERSECT ALL
(SELECT FIRST_NAME FROM CUSTOMER)

(SELECT FIRST_NAME FROM ACTOR)
EXCEPT ALL
(SELECT FIRST_NAME FROM CUSTOMER)
~~~

## <p id = 'Ödev 12' > Ödev 12 </p>
#### Film tablosunda film uzunluğu length sütununda gösterilmektedir. Uzunluğu ortalama film uzunluğundan fazla kaç tane film vardır?
~~~sql
SELECT COUNT(DISTINCT(FILM_ID))FROM FILM
WHERE LENGTH > 
(SELECT AVG(LENGTH) FROM FILM)
~~~
#### Film tablosunda en yüksek rental_rate değerine sahip kaç tane film vardır?

~~~sql
SELECT COUNT(DISTINCT(FILM_ID))FROM FILM
WHERE RENTAL_RATE = 
(SELECT MAX(RENTAL_RATE) FROM FILM)
~~~
#### Film tablosunda en düşük rental_rate ve en düşün replacement_cost değerlerine sahip filmleri sıralayınız.

~~~sql
SELECT TITLE FROM FILM
WHERE (RENTAL_RATE = (SELECT MIN(RENTAL_RATE) FROM FILM)) AND  (REPLACEMENT_COST = (SELECT MIN(REPLACEMENT_COST) FROM FILM))
~~~

#### Payment tablosunda en fazla sayıda alışveriş yapan müşterileri(customer) sıralayınız.

~~~sql
SELECT CUSTOMER_ID,COUNT(PAYMENT_ID) FROM PAYMENT
GROUP BY CUSTOMER_ID
ORDER BY COUNT DESC
LIMIT 1
~~~
