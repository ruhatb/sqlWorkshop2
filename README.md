# sqlWorkshop2

--Her kategorideki (CategoryID) ürün sayısını gösteren--
SELECT 
	categoryid, 
    count(*) FROM products 
group by categoryid
ORDER BY categoryid

--Birim fiyatı en yüksek 5 ürünü listeleyin --
SELECT * FROM Products
ORDER BY unitprice DESC LIMIT 5

--Her tedarikçinin sattığı ürünlerin ortalama fiyatını listeleyin.
SELECT 
	supplierid,
    AVG(unitprice) FROM products
group by supplierid

--En son sevk edilen 10 siparişi listeleyin--
SELECT *FROM orders
ORDER BY shippeddate DESC
LIMIT 10

-Products tablosunda fiyatı 50’den büyük olan ürünlerin toplam stok miktarını hesaplayın--
SELECT SUM(unitsinstock) FROM products
WHERE unitprice > 50 

--OrderDetails tablosundaki her bir sipariş için, birim fiyatın toplamını yuvarlayarak (ROUND) hesaplayın--

SELECT orderID, ROUND(SUM(unitPrice), 2) AS TotalUnitPrice FROM 'Order Details'
GROUP BY orderID


--Employees tablosundaki çalışanların tam adını (FirstName + LastName) birleştirerek gösterin--
SELECT CONCAT(firstname, ' ', lastname) as [fullname] FROM employees

--Customers tablosundaki şehir adlarının uzunluğunu (LENGTH) hesaplayın--
SELECT city, LENGTH(city)
FROM customers
WHERE CITY IS NOT NULL
GROUP BY city


--Products tablosundaki en yüksek en düşük fiyat göstrein --
SELECT MIN(unitPrice) AS MinPrice, MAX(unitPrice) AS MaxPrice
FROM Products

--Orders tablosunda her yıl kaç sipariş alındığını listeleyin (YEAR() fonksiyonunu kullanarak)--

SELECT STRFTIME('%Y', OrderDate) AS OrderYear, COUNT(*) AS OrderCount FROM Orders
GROUP BY OrderYear

--Productstablosundaki en pahalı ürünün fiyatını bulun ve bir fonksiyon kullanarak fiyatı 10% artırın.
SELECT * FROM products

--Products tablosundaki ürün adlarının ilk 3 karakterini gösterin (SUBSTRING)--
SELECT * FROM products

