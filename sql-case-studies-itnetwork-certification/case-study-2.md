Case Study 02 — E-commerce Product Analytics
Cíl projektu

Procvičit SQL dotazy používané v základní datové analytice na realistickém e-commerce scénáři.

Projekt simuluje databázi produktů internetového obchodu a zaměřuje se na:

filtrování dat
agregace
business reporting
práci s kategoriemi
analytické myšlení nad datasety
Procvičené dovednosti
SELECT
WHERE
AND / OR
LIKE
IN
BETWEEN
ORDER BY
TOP
COUNT
SUM
AVG
MIN / MAX
GROUP BY
HAVING
Business scénář

E-shop potřebuje analyzovat své produkty a skladová data.

Management chce:

identifikovat drahé produkty
analyzovat kategorie produktů
spočítat hodnotu skladu
zjistit průměrné ceny produktů
identifikovat nejdražší produkty a nejvýnosnější kategorie
Dataset
CREATE TABLE products (
    product_id INT PRIMARY KEY,
    product_name NVARCHAR(100),
    category NVARCHAR(50),
    price INT,
    stock INT
);

INSERT INTO products VALUES
(1, 'iPhone 15', 'Elektronika', 26000, 5),
(2, 'Samsung TV', 'Elektronika', 18000, 2),
(3, 'Herní židle', 'Nábytek', 6500, 8),
(4, 'Notebook Lenovo', 'Elektronika', 22000, 4),
(5, 'Psací stůl', 'Nábytek', 4500, 10),
(6, 'Power BI kurz', 'Kurzy', 3000, 50),
(7, 'SQL kurz', 'Kurzy', 2500, 40),
(8, 'Python kurz', 'Kurzy', 4000, 35),
(9, 'Monitor Dell', 'Elektronika', 7000, 7),
(10, 'Kancelářská židle', 'Nábytek', 3500, 12);

Zadání

1. Výpis produktů dražších než 10 000
SELECT *
FROM products
WHERE price > 10000;

2. Výpis produktů z kategorie Elektronika se skladem menším než 5
SELECT *
FROM products
WHERE category = 'Elektronika'
AND stock < 5;

3. Výpis produktů z kategorií Elektronika nebo Kurzy
SELECT *
FROM products
WHERE category IN ('Elektronika', 'Kurzy');

4. Výpis 3 nejdražších produktů
SELECT TOP 3 *
FROM products
ORDER BY price DESC;

5. Průměrná cena všech produktů
SELECT
    AVG(price) AS average_price
FROM products;

6. Nejvyšší a nejnižší cena produktu
SELECT
    MAX(price) AS max_price,
    MIN(price) AS min_price
FROM products;

7. Celková hodnota skladu
SELECT
    SUM(price * stock) AS stock_value
FROM products;

8. Počet produktů podle kategorií
SELECT
    category,
    COUNT(*) AS total_products
FROM products
GROUP BY category;

9. Průměrná cena podle kategorií
SELECT
    category,
    AVG(price) AS avg_price_category
FROM products
GROUP BY category;

10. Kategorie s více než 2 produkty
SELECT
    category,
    COUNT(*) AS product_numbers
FROM products
GROUP BY category
HAVING COUNT(*) > 2;

11. Kategorie s nejvyšší průměrnou cenou
SELECT TOP 1
    category,
    AVG(price) AS avg_price
FROM products
GROUP BY category
ORDER BY avg_price DESC;

Očekávaný výsledek
Kategorie s nejvyšší průměrnou cenou
category	avg_price
Elektronika	18250

Co jsem se naučil
SQL umí efektivně analyzovat business data
WHERE filtruje jednotlivé řádky
GROUP BY agreguje data do skupin
HAVING filtruje agregované výsledky
ORDER BY umožňuje ranking a prioritizaci
agregační funkce jsou základ business reportingu
SQL je velmi vhodné pro analytické úlohy
Využití v praxi

Tato case study simuluje běžné úkoly datového analytika v e-commerce:

produktová analytika
reporting skladů
cenová analytika
business intelligence
retail reporting
dashboarding v Power BI
Poznámka autora

Projekt vznikl jako součást osobní SQL learning journey inspirované kurzem ITnetwork MS-SQL.

Business scénář i datasety byly vytvořeny jako vlastní originální varianta pro studijní a portfolio účely.
