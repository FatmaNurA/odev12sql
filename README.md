# odev12sql

### film tablosunda film uzunluğu length sütununda gösterilmektedir. Uzunluğu ortalama film uzunluğundan fazla kaç tane film vardır?
SELECT COUNT(*) FROM film
WHERE lenght >
( 
  SELECT AVG (length) FROM film
);
### film tablosunda en yüksek rental_rate değerine sahip kaç tane film vardır?
SELECT COUNT(*) FROM film
WHERE rental_rate
( 
  SELECT MAX(rental_rate) FROM film
);
### film tablosunda en düşük rental_rate ve en düşün replacement_cost değerlerine sahip filmleri sıralayınız.
SELECT title FROM film
WHERE rental_rate ANY
( 
  SELECT MIN(rental_rate) OR MIN(replacement_cost) FROM film
);
### payment tablosunda en fazla sayıda alışveriş yapan müşterileri(customer) sıralayınız.
SELECT customer FROM payment
...
