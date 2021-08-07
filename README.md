# PatikaDev-PostgreSQL

<a href='#Ödev 1'>Ödev 1</a><br>
<a href='#Ödev 2'>Ödev 2</a><br>
<a href='#Ödev 3'>Ödev 3</a><br>
<a href='#Ödev 4'>Ödev 4</a><br>
<a href='#Ödev 5'>Ödev 5</a><br>
<a href='#Ödev 6'>Ödev 6</a><br>
<a href='#Ödev 7'>Ödev 7</a><br>

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


