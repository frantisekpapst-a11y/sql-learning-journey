📘 Lekce 1 – Vytvoření databáze a tabulky

❓ Otázky
Jaké základní datové typy jsme používali?
Co dělá IDENTITY?
Co znamená NOT NULL?
K čemu slouží PRIMARY KEY?
Jaký SQL příkaz vytváří tabulku?

✅ Odpovědi
INT, NVARCHAR, DATE.
Automatické číslování záznamů.
Hodnota nesmí být prázdná.
K unikátní identifikaci záznamů.
CREATE TABLE.

📘 Lekce 2 – Vkládání a mazání dat

❓ Otázky
Proč při INSERT často neuvádíme sloupec Id?
Co udělá tento dotaz?
UPDATE [Knihy]
SET [PocetStran] = 500;
Jaký je rozdíl mezi DELETE a TRUNCATE TABLE?
Co je SQL Injection?
Co znamená CRUD?

✅ Odpovědi
Databáze ho vyplní sama díky IDENTITY.
U všech záznamů změní PocetStran na 500.
DELETE maže konkrétní řádky (často přes WHERE), TRUNCATE smaže všechna data v tabulce.
Bezpečnostní útok přes manipulaci SQL dotazu.
Create, Read, Update, Delete.

📘 Lekce 3 – Export databáze

❓ Otázky
Jaké existují typy exportu?
K čemu slouží SET IDENTITY_INSERT?
Co znamená export struktury?
Co vrátí:
SELECT *
FROM [Uzivatele];
Jaký je rozdíl mezi DELETE a TRUNCATE?
Jakým příkazem vkládáme data?
Jakým příkazem upravujeme data?
Proč je důležité používat WHERE?
Co znamená CRUD?

✅ Odpovědi
Kompletní export, export struktury, export dat.
Umožní ručně vložit hodnoty do IDENTITY sloupce.
Export pouze struktury tabulek bez dat.
Všechny řádky a sloupce tabulky.
DELETE může mazat podmíněně, TRUNCATE smaže vše a resetuje IDENTITY.
INSERT INTO.
UPDATE.
Aby se neupravily všechny řádky v tabulce.
Create, Read, Update, Delete.

📘 Lekce 4 – Import databáze

❓ Otázky
Co je .dacpac?
Jaký je rozdíl mezi importem dat a importem tabulky?
Proč používáme SET IDENTITY_INSERT ON?
Co dělá příkaz USE?
Co udělá DROP TABLE?
Jaký příkaz vytváří tabulku?
Jaký příkaz smaže tabulku?
Jaký příkaz smaže data?
Co znamená CRUD?

✅ Odpovědi
Soubor pro přenos celé databáze (struktura + data).
Import dat plní existující tabulku, import tabulky ji vytváří.
Aby šlo ručně nastavovat hodnoty ID.
Přepne aktivní databázi.
Úplně smaže tabulku i její strukturu.
CREATE TABLE.
DROP TABLE.
DELETE nebo TRUNCATE TABLE.
Create, Read, Update, Delete.

📘 Lekce 5 – Kvíz a opakování

❓ Otázky
Pokud chceme pomocí SQL získat data:
SQL neslouží k získávání dat z databáze.
SQL vrátí vždy výpis všech dat v databázi.
Řekneme databázi přesný postup, jak data získat.
Řekneme pouze, co má být výsledkem.
Co dělá:
TRUNCATE TABLE [Uzivatele];
Co NEmůžeme importovat?
Data
Celou tabulku
Databázi s daty bez tabulek
Celou databázi

✅ Odpovědi

✅ Řekneme pouze, co má být výsledkem.

✅ Vymaže všechny záznamy z tabulky.

✅ Databázi s daty bez tabulek.

📘 Bonus – Rozdíly mezi DELETE / TRUNCATE / DROP

❓ Otázky
Jaký je rozdíl mezi DROP a DELETE?
Jaký je rozdíl mezi DROP a TRUNCATE?
Jaký je rozdíl mezi DELETE a TRUNCATE?

✅ Odpovědi
1. DROP vs DELETE
DROP	DELETE
smaže tabulku	smaže data
smaže strukturu	strukturu zachová
tabulka přestane existovat	tabulka zůstane
2. DROP vs TRUNCATE
DROP	TRUNCATE
smaže tabulku	smaže jen data
smaže strukturu	strukturu zachová
tabulka zmizí	tabulka zůstane
3. DELETE vs TRUNCATE
DELETE	TRUNCATE
může mít WHERE	nemá WHERE
maže postupně	smaže vše najednou
neresetuje IDENTITY	resetuje IDENTITY
pomalejší	rychlejší
