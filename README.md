# MYSQL

### CRIAR DATABASE
```
CREATE database Products;

USE Products;
```
### CRIAR TABELA
```
CREATE TABLE Categories (
	CategoryID INT auto_increment primary key,
    CategoryName varchar(50),
    Description text (150)
);
```
```
create table Suppliers (
	SupplierID int auto_increment primary key,
    SupplierName varchar(50),
    ContactName varchar(50),
    Address varchar(50),
    City varchar(50),
    PostalCode varchar(10),
    Country varchar(20),
    Phone varchar(20)
);
```
```
CREATE TABLE Products (
    ProductID INT AUTO_INCREMENT PRIMARY KEY,
    ProductName VARCHAR(50),
    SupplierID INT,
    CategoryID INT,
    Unit VARCHAR(100),
    Price FLOAT,
    FOREIGN KEY (SupplierID) REFERENCES Suppliers(SupplierID),
    FOREIGN KEY (CategoryID) REFERENCES Categories(CategoryID)
);
```
### INSERIR DADOS NA TABELA
```
INSERT INTO Suppliers (SupplierName, ContactName, Address, City, PostalCode, Country, Phone)
VALUES
	('Exotic Liquid', 'Charlotte Cooper', '49 Gilbert St.', 'London', 'EC1 4SD', 'UK', '(171) 555-2222'),
    ('Tokyo Traders', 'Yoshi Nagase', '9-8 Sekimai Musashino-shi', 'Tokyo', '100', 'Japan', '(03) 3555-5011'),
    ('Cooperativa de Quesos ''Las Cabras''', 'Antonio del Valle Saavedra', 'Calle del Rosal 4', 'Oviedo', '33007', 'Spain', '(98) 598 76 54'),
    ('Mayumi''s', 'Mayumi Ohno', '92 Setsuko Chuo-ku', 'Osaka', '545', 'Japan', '(06) 431-7877'),
    ('Pavlova, Ltd.', 'Ian Devling', '74 Rose St. Moonie Ponds', 'Melbourne', '3058', 'Australia', '(03) 444-2343'),
    ('Specialty Biscuits, Ltd.', 'Peter Wilson', '29 King''s Way', 'Manchester', 'M14 GSD', 'UK', '(161) 555-4448'),
    ('PB Knäckebröd AB', 'Lars Peterson', 'Kaloadagatan 13', 'Göteborg', 'S-345 67', 'Sweden', '031-987 65 43'),
    ('Refrescos Americanas LTDA', 'Carlos Diaz', 'Av. das Americanas 12.890', 'São Paulo', '5442', 'Brazil', '(11) 555 4640'),
    ('Heli Süßwaren GmbH & Co. KG', 'Petra Winkler', 'Tiergartenstraße 5', 'Berlin', '10785', 'Germany', '(010) 9984510'),
    ('Plutzer Lebensmittelgroßmärkte AG', 'Martin Bein', 'Bogenallee 51', 'Frankfurt', '60439', 'Germany', '(069) 992755'),
    ('Nord-Ost-Fisch Handelsgesellschaft mbH', 'Sven Petersen', 'Frahmredder 112a', 'Cuxhaven', '27478', 'Germany', '(04721) 8713'),
    ('Formaggi Fortini s.r.l.', 'Elio Rossi', 'Viale Dante, 75', 'Ravenna', '48100', 'Italy', '(0544) 60323'),
    ('Norske Meierier', 'Beate Vileid', 'Hatlevegen 5', 'Sandvika', '1320', 'Norway', '(0)2-953010'),
    ('Bigfoot Breweries', 'Cheryl Saylor', '3400 - 8th Avenue Suite 210', 'Bend', '97101', 'USA', '(503) 555-9931'),
    ('Svensk Sjöföda AB', 'Michael Björn', 'Brovallavägen 231', 'Stockholm', 'S-123 45', 'Sweden', '08-123 45 67'),
    ('Aux joyeux ecclésiastiques', 'Guylène Nodier', '203, Rue des Francs-Bourgeois', 'Paris', '75004', 'France', '(1) 03.83.00.68'),
    ('New England Seafood Cannery', 'Robb Merchant', 'Order Processing Dept. 2100 Paul Revere Blvd.', 'Boston', '2134', 'USA', '(617) 555-3267'),
    ('Leka Trading', 'Chandra Leka', '471 Serangoon Loop, Suite #402', 'Singapore', '512', 'Singapore', '555-8787'),
    ('Lyngbysild', 'Niels Petersen', 'Lyngbysild Fiskebakken 10', 'Lyngby', '2800', 'Denmark', '43844108'),
    ('Zaanse Snoepfabriek', 'Dirk Luchte', 'Verkoop Rijnweg 22', 'Zaandam', '9999 ZZ', 'Netherlands', '(12345) 1212'),
    ('Karkki Oy', 'Anne Heikkonen', 'Valtakatu 12', 'Lappeenranta', '53120', 'Finland', '(953) 10956'),
    ('G''day, Mate', 'Wendy Mackenzie', '170 Prince Edward Parade Hunter''s Hill', 'Sydney', '2042', 'Australia', '(02) 555-5914'),
    ('Ma Maison', 'Jean-Guy Lauzon', '2960 Rue St. Laurent', 'Montréal', 'H1J 1C3', 'Canada', '(514) 555-9022'),
    ('Pasta Buttini s.r.l.', 'Giovanni Giudici', 'Via dei Gelsomini, 153', 'Salerno', '84100', 'Italy', '(089) 6547665'),
    ('Escargots Nouveaux', 'Marie Delamare', '22, rue H. Voiron', 'Montceau', '71300', 'France', '85.57.00.07'),
    ('Gai pâturage', 'Eliane Noz', 'Bat. B 3, rue des Alpes', 'Annecy', '74000', 'France', '38.76.98.06'),
    ('Forêts d''érables', 'Chantal Goulet', '148 rue Chasseur', 'Ste-Hyacinthe', 'J2S 7S8', 'Canada', '(514) 555-2955');
```

```
INSERT INTO Categories (CategoryName, Description)
VALUES
	('Beverages', 'Soft drinks, coffees, teas, beers, and ales'),
    ('Condiments', 'Sweet and savory sauces, relishes, spreads, and seasonings'),
    ('Confections', 'Desserts, candies, and sweet breads'),
    ('Dairy Products', 'Cheeses'),
    ('Grains/Cereals', 'Breads, crackers, pasta, and cereal'),
    ('Meat/Poultry', 'Prepared meats'),
    ('Produce', 'Dried fruit and bean curd'),
    ('Seafood', 'Seaweed and fish');
```

```
INSERT INTO Products (ProductName, SupplierID, CategoryID, Unit, Price)
VALUES 
	('Chais', 1, 1, '10 boxes x 20 bags', 18),
    ('Chang', 1, 1, '24 - 12 oz bottles', 19),
    ('Aniseed Syrup', 1, 2, '12 - 550 ml bottles', 10),
    ('Chef Anton''s Cajun Seasoning', 2, 2, '48 - 6 oz jars', 22),
    ('Chef Anton''s Gumbo Mix', 2, 2, '36 boxes', 21.35),
    ('Grandma''s Boysenberry Spread', 3, 2, '12 - 8 oz jars', 25),
    ('Uncle Bob''s Organic Dried Pears', 3, 7, '12 - 1 lb pkgs.', 30),
    ('Northwoods Cranberry Sauce', 3, 2, '12 - 12 oz jars', 40),
    ('Mishi Kobe Niku', 4, 6, '18 - 500 g pkgs.', 97),
    ('Ikura', 4, 8, '12 - 200 ml jars', 31),
    ('Queso Cabrales', 5, 4, '1 kg pkg.', 21),
    ('Queso Manchego La Pastora', 5, 4, '10 - 500 g pkgs.', 38),
    ('Konbu', 6, 8, '2 kg box', 6),
    ('Tofu', 6, 7, '40 - 100 g pkgs.', 23.25),
    ('Genen Shouyu', 6, 2, '24 - 250 ml bottles', 15.5),
    ('Pavlova', 7, 3, '32 - 500 g boxes', 17.45),
    ('Alice Mutton', 7, 6, '20 - 1 kg tins', 39),
    ('Carnarvon Tigers', 7, 8, '16 kg pkg.', 62.5),
    ('Teatime Chocolate Biscuits', 8, 3, '10 boxes x 12 pieces', 9.2),
    ('Sir Rodney''s Marmalade', 8, 3, '30 gift boxes', 81),
    ('Sir Rodney''s Scones', 8, 3, '24 pkgs. x 4 pieces', 10),
    ('Gustaf''s Knäckebröd', 9, 5, '24 - 500 g pkgs.', 21),
    ('Tunnbröd', 9, 5, '12 - 250 g pkgs.', 9),
    ('Guaraná Fantástica', 10, 1, '12 - 355 ml cans', 4.5),
    ('NuNuCa Nuß-Nougat-Creme', 11, 3, '20 - 450 g glasses', 14),
    ('Gumbär Gummibärchen', 11, 3, '100 - 250 g bags', 31.23),
    ('Schoggi Schokolade', 11, 3, '100 - 100 g pieces', 43.9),
    ('Rössle Sauerkraut', 12, 7, '25 - 825 g cans', 45.6),
    ('Thüringer Rostbratwurst', 12, 6, '50 bags x 30 sausgs.', 123.79),
    ('Nord-Ost Matjeshering', 13, 8, '10 - 200 g glasses', 25.89),
    ('Gorgonzola Telino', 14, 4, '12 - 100 g pkgs', 12.5),
    ('Mascarpone Fabioli', 14, 4, '24 - 200 g pkgs.', 32),
    ('Geitost', 15, 4, '500 g', 2.5),
    ('Sasquatch Ale', 16, 1, '24 - 12 oz bottles', 14),
    ('Steeleye Stout', 16, 1, '24 - 12 oz bottles', 18),
    ('Inlagd Sill', 17, 8, '24 - 250 g jars', 19),
    ('Gravad lax', 17, 8, '12 - 500 g pkgs.', 26),
    ('Côte de Blaye', 18, 1, '12 - 75 cl bottles', 263.5),
    ('Chartreuse verte', 18, 1, '750 cc per bottle', 18),
    ('Boston Crab Meat', 19, 8, '24 - 4 oz tins', 18.4),
    ('Jack''s New England Clam Chowder', 19, 8, '12 - 12 oz cans', 9.65),
    ('Singaporean Hokkien Fried Mee', 20, 5, '32 - 1 kg pkgs.', 14),
    ('Ipoh Coffee', 20, 1, '16 - 500 g tins', 46),
    ('Gula Malacca', 20, 2, '20 - 2 kg bags', 19.45),
    ('Røgede sild', 21, 8, '1k pkg.', 9.5),
    ('Spegesild', 21, 8, '4 - 450 g glasses', 12),
    ('Zaanse koeken', 22, 3, '10 - 4 oz boxes', 9.5),
    ('Chocolade', 22, 3, '10 pkgs.', 12.75),
    ('Maxilaku', 23, 3, '24 - 50 g pkgs.', 20),
    ('Valkoinen suklaa', 23, 3, '12 - 100 g bars', 16.25),
    ('Manjimup Dried Apples', 24, 7, '50 - 300 g pkgs.', 53),
    ('Filo Mix', 24, 5, '16 - 2 kg boxes', 7),
    ('Perth Pasties', 24, 6, '48 pieces', 32.8),
    ('Tourtière', 25, 6, '16 pies', 7.45),
    ('Pâté chinois', 25, 6, '24 boxes x 2 pies', 24),
    ('Gnocchi di nonna Alice', 26, 5, '24 - 250 g pkgs.', 38),
    ('Ravioli Angelo', 26, 5, '24 - 250 g pkgs.', 19.5),
    ('Escargots de Bourgogne', 27, 8, '24 pieces', 13.25),
    ('Raclette Courdavault', 28, 4, '5 kg pkg.', 55),
    ('Camembert Pierrot', 28, 4, '15 - 300 g rounds', 34),
    ('Sirop d''érable', 29, 2, '24 - 500 ml bottles', 28.5),
    ('Tarte au sucre', 29, 3, '48 pies', 49.3),
    ('Vegie-spread', 7, 2, '15 - 625 g jars', 43.9),
    ('Wimmers gute Semmelknödel', 12, 5, '20 bags x 4 pieces', 33.25),
    ('Louisiana Fiery Hot Pepper Sauce', 2, 2, '32 - 8 oz bottles', 21.05),
    ('Louisiana Hot Spiced Okra', 2, 2, '24 - 8 oz jars', 17),
    ('Laughing Lumberjack Lager', 16, 1, '24 - 12 oz bottles', 14),
    ('Scottish Longbreads', 8, 3, '10 boxes x 8 pieces', 12.5),
    ('Gudbrandsdalsost', 15, 4, '10 kg pkg.', 36),
    ('Outback Lager', 7, 1, '24 - 355 ml bottles', 15),
    ('Fløtemysost', 15, 4, '10 - 500 g pkgs.', 21.5),
    ('Mozzarella di Giovanni', 14, 4, '24 - 200 g pkgs.', 34.8),
    ('Röd Kaviar', 17, 8, '24 - 150 g jars', 15),
    ('Longlife Tofu', 4, 7, '5 kg pkg.', 10),
    ('Rhönbräu Klosterbier', 12, 1, '24 - 0.5 l bottles', 7.75),
    ('Lakkalikööri', 23, 1, '500 ml', 18),
    ('Original Frankfurter grüne Soße', 12, 2, '12 boxes', 13);
```

### VISUALIZAR DADOS
```
SELECT * FROM Suppliers;
SELECT * FROM Categories; 
SELECT * FROM Products;
```

### WHERE E BETWEEN 
```
SELECT * FROM Products WHERE ProductID = 156; -- EXIBE O DADO DO ID DE 155
SELECT * FROM Products WHERE ProductID BETWEEN 155 AND 160; -- EXIBE ID DE 155 A 160
SELECT * FROM Products WHERE SupplierID BETWEEN 2 AND 6 AND CategoryID BETWEEN 2 AND 6; 
SELECT * FROM Products WHERE SupplierID = 2 AND CategoryID = 2; -- ENCONTRANDO ID DE NÚMERO 2 DAS DUAS TABELAS
```


# SCRIPTS DE SQL ORACLE 
* Link utilizado para pratica: 
https://www.w3schools.com/sql/trysql.asp?filename=trysql_products

### Exemplos

#### - Encontrar dados iguais de diferentes atributos(WHERE)
Para encontrar IDs que equivalem ao número 2:

![image](https://github.com/is-Isadora-Rocha/SQL-Oracle/assets/115477897/02b31cf3-92db-4d9c-9d64-24b91a978c73)


```
SELECT * FROM Products WHERE SupplierID = 2 AND CategoryID = 2
```

![image](https://github.com/is-Isadora-Rocha/SQL-Oracle/assets/115477897/29ad40b7-208c-4aed-93a4-3e072b563290)


#### Outro exemplo:
```
SELECT * FROM Products WHERE CategoryID >= 2 AND Price <= 7;
```
![image](https://github.com/is-Isadora-Rocha/SQL-Oracle/assets/115477897/7cfba52a-e636-4dbd-98f4-6ef544c00fb7)


### BETWEEN

```
SELECT * FROM Products WHERE SupplierID BETWEEN 2 AND 6
							AND CategoryID BETWEEN 2 AND 6;
```
![image](https://github.com/is-Isadora-Rocha/SQL-Oracle/assets/115477897/72c55175-3f92-4eec-b061-caedc29504f1)
