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
