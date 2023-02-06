1. **Создайте таблицу с мобильными телефонами, используя графический интерфейс. Необходимые поля таблицы: product_name (название товара), manufacturer (производитель), product_count (количество), price (цена).** 
``` 
CREATE TABLE `HomeWork1`.`Phones` (
  `idnew_table` INT NOT NULL AUTO_INCREMENT,
  `product_name` VARCHAR(45) NOT NULL,
  `manufacturer` VARCHAR(45) NOT NULL,
  `product_count` INT NULL,
  `colprice` VARCHAR(45) NULL,
  UNIQUE INDEX `idnew_table_UNIQUE` (`idnew_table` ASC) VISIBLE,
  PRIMARY KEY (`idnew_table`));
```
**Заполните БД произвольными данными.**

```
INSERT INTO `HomeWork1`.`Phones` (`idnew_table`, `product_name`, `manufacturer`, `product_count`, `colprice`) VALUES ('1245', 'Motorola-110T', 'Japan', '5', '1500');
INSERT INTO `HomeWork1`.`Phones` (`idnew_table`, `product_name`, `manufacturer`, `product_count`, `colprice`) VALUES ('4567', 'Sony-Ericson', 'Japan', '10', '2500');
INSERT INTO `HomeWork1`.`Phones` (`idnew_table`, `product_name`, `manufacturer`, `product_count`, `colprice`) VALUES ('43728', 'YO-Phone', 'Russia', '0', '1000000');
INSERT INTO `HomeWork1`.`Phones` (`idnew_table`, `product_name`, `manufacturer`, `product_count`, `colprice`) VALUES ('3256', 'Iphone-10', 'USA', '15', '100000');
INSERT INTO `HomeWork1`.`Phones` (`idnew_table`, `product_name`, `manufacturer`, `product_count`, `colprice`) VALUES ('4569', 'Samsung', 'S.Korea', '30', '15000');
INSERT INTO `HomeWork1`.`Phones` (`idnew_table`, `product_name`, `manufacturer`, `product_count`, `colprice`) VALUES ('23', 'Nokia-3310', 'Swiezerland', '6', '5000');
INSERT INTO `HomeWork1`.`Phones` (`idnew_table`, `product_name`, `manufacturer`, `product_count`, `colprice`) VALUES ('4637', 'Iphon-8', 'USA', '3', '50000');
INSERT INTO `HomeWork1`.`Phones` (`idnew_table`, `product_name`, `manufacturer`, `product_count`, `colprice`) VALUES ('43678', 'Samsung-456L', 'S.Korea', '14', '30000');
INSERT INTO `HomeWork1`.`Phones` (`idnew_table`, `product_name`, `manufacturer`, `product_count`, `colprice`) VALUES ('124', 'Siemens-M65', 'Germany', '20', '7000');
```
2. **Напишите SELECT-запрос, который выводит название товара, производителя и цену для товаров, количество которых превышает 2**
```
USE HomeWork1;

SELECT product_name, manufacturer, colprice FROM Phones
where product_count > 2;
```
3. **Выведите SELECT-запросом весь ассортимент товаров марки “Samsung”**  
Если в названии присутствует ещё знаки(буквы/цифры), то этот телефон не появится. Для этого существует команда "LIKE", её работа указана в пункте 4.2 

```
USE HomeWork1;

SELECT * FROM Phones
WHERE product_name = 'Samsung';
```
4. **С помощью SELECT-запроса с оператором LIKE / REGEXP найти:**  

**4.1 Товары, в которых есть упоминание "Iphone"**
```
USE HomeWork1;

SELECT * FROM Phones
WHERE product_name LIKE '%Iphon%';
```
**4.2 Товары, в которых есть упоминание "Samsung"**
```
USE HomeWork1;

SELECT * FROM Phones
WHERE product_name LIKE '%Samsung%';
```
**4.3 Товары, в названии которых есть ЦИФРЫ**
```
USE HomeWork1;

SELECT * FROM Phones
WHERE product_name REGEXP '[0-9]';
```
**4.4 Товары, в названии которых есть ЦИФРА "8"**
```
USE HomeWork1;

SELECT * FROM Phones
WHERE product_name REGEXP '[8]';
```