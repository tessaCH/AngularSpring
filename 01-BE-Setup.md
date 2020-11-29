## Back End
### Installation
Pre-install: IntelliJ, Java, Tomcat, MySQL(8.0.4), Postman</br>
For the MySQL Reference Manual, visit: [MySQL Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/caching-sha2-pluggable-authentication.html)</br>
For Postman, visit: [getPostman](https://www.postman.com/downloads/)</br>

### MySQL Database Setup
#### Create MySQL User
```
CREATE USER 'angularspringapp'@'localhost' IDENTIFIED BY 'angularspringapp';
GRANT ALL PRIVILEGES ON * . * TO 'angularspringapp'@'localhost';
ALTER USER 'angularspringapp'@'localhost' IDENTIFIED WITH mysql_native_password BY 'angularspringapp';
```
#### Create MySQL Database
```
DROP SCHEMA IF EXISTS `full-stack-ecommerce`;

CREATE SCHEMA `full-stack-ecommerce`;
USE `full-stack-ecommerce` ;

-- -----------------------------------------------------
-- Table `full-stack-ecommerce`.`product_category`
-- -----------------------------------------------------
CREATE TABLE IF NOT EXISTS `full-stack-ecommerce`.`product_category` (
  `id` BIGINT(20) NOT NULL AUTO_INCREMENT,
  `category_name` VARCHAR(255) NULL DEFAULT NULL,
  PRIMARY KEY (`id`))
ENGINE=InnoDB
AUTO_INCREMENT = 1;

-- -----------------------------------------------------
-- Table `full-stack-ecommerce`.`product`
-- -----------------------------------------------------
CREATE TABLE IF NOT EXISTS `full-stack-ecommerce`.`product` (
  `id` BIGINT(20) NOT NULL AUTO_INCREMENT,
  `sku` VARCHAR(255) DEFAULT NULL,
  `name` VARCHAR(255) DEFAULT NULL,
  `description` VARCHAR(255) DEFAULT NULL,
  `unit_price` DECIMAL(13,2) DEFAULT NULL,
  `image_url` VARCHAR(255) DEFAULT NULL,
  `active` BIT DEFAULT 1,
  `units_in_stock` INT(11) DEFAULT NULL,
   `date_created` DATETIME(6) DEFAULT NULL,
  `last_updated` DATETIME(6) DEFAULT NULL,
  `category_id` BIGINT(20) NOT NULL,
  PRIMARY KEY (`id`),
  KEY `fk_category` (`category_id`),
  CONSTRAINT `fk_category` FOREIGN KEY (`category_id`) REFERENCES `product_category` (`id`)
) 
ENGINE=InnoDB
AUTO_INCREMENT = 1;
```

### Spring Initializr
From Spring Initializr Website</br>
> Generate starter file, visit: [Spring Initializr Website](https://start.spring.io/)</br>
From IntelliJ</br>
> `New Project -> Spring Initializr -> Project SDK: "15"->Default: https://start.spring.io ->`
#### Related Options
```
Tyep: Maven
Language: Java
Packaging: Jar
Java Version: 11
```
