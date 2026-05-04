# SecondWearClothing

# SecondWear – Sustainable Campus Fashion Exchange
SecondWear is a web‑based peer‑to‑peer marketplace where students can buy
and sell pre‑loved clothes **within their own campus community**.
The platform includes secure escrow payments, admin verification of new
users, and a complete shopping cart experience.
---
## Features
- **User registration & login** – with pending admin approval (no instant
login)
- **Admin dashboard** – verify new users, add/edit/delete customers
- **Product listings** – browse clothes by gender, category, campus, and
price
- **Shopping cart** – add items, update quantities, and proceed to
checkout
- **Sell your clothes** – upload photos and create listings (stored in
`localStorage`)
- **Secure password storage** – bcrypt hashing
- **Responsive design** – works on desktop and mobile
---
## Technologies Used
| Component | Technology |
|----------------|--------------------------------------|
| Frontend | HTML5, CSS3, JavaScript (vanilla) |
| Backend | PHP 8.0+ (MySQLi) |
| Database | MySQL (MariaDB) |
| Icons | FontAwesome 6 |
| Fonts | Google Fonts (Inter) |
| Local storage | Cart and user‑uploaded product data |
---
## Project Structure

---
## Database Schema
The database is named `ClothingStore` and contains the following tables:
### `tblUser`
| Column | Type | Description |
|-------------|----------------------|---------------------------------|
| UserID | INT (PK) | Auto‑increment |
| FullName | VARCHAR(100) | User’s full name |
| Email | VARCHAR(100) UNIQUE | Login credential |
| Password | VARCHAR(255) | bcrypt hash |
| Campus | VARCHAR(100) | e.g. Pretoria Campus |
| Status | ENUM('pending','verified') | Admin approval status |
| CreatedAt | DATETIME | Auto timestamp |
### `tblAdmin`
| Column | Type | Description |
|-----------|--------------|-----------------------|
| AdminID | INT (PK) | Auto‑increment |
| FullName | VARCHAR(100) | Admin’s name |
| Email | VARCHAR(100) UNIQUE | Login credential |
| Password | VARCHAR(255) | bcrypt hash |
| CreatedAt | DATETIME | Auto timestamp |
### `tblClothes`
| Column | Type | Description
| |
---------------|-------------------------------|------------------------
---------|
| ClothesID | INT (PK) | Auto‑increment
|
| Name | VARCHAR(100) | Product name
|
| Description | TEXT | Item details
|
| Price | DECIMAL(10,2) | Selling price
|
| Size | VARCHAR(10) | XS, S, M, L, XL, etc.
|
| Category | VARCHAR(50) | Dresses, Tops, Jackets,
… |
| Gender | ENUM('men','women','unisex') |
|
| Brand | VARCHAR(50) | Zara, Nike, H&M, …
|
| ItemCondition | VARCHAR(50) | Like New, Excellent,
Good |
| Campus | VARCHAR(100) | Listing campus
|
| SellerID | INT (FK → tblUser.UserID) | Seller reference
|
| CreatedAt | DATETIME | Auto timestamp
|
### `tblAorder` (Orders)| Column | Type | Description |
|------------|---------------|---------------------------------|
| OrderID | INT (PK) | Auto‑increment |
| UserID | INT (FK) | Buyer (tblUser.UserID) |
| ClothesID | INT (FK) | Product (tblClothes.ClothesID) |
| Quantity | INT | Number of items |
| TotalPrice | DECIMAL(10,2) | Price × Quantity |
| OrderDate | DATETIME | Auto timestamp |
| Status | VARCHAR(50) | Pending, Shipped, Delivered |
---
## Installation & Setup
### 1. Prerequisites
- **XAMPP** (or any LAMP/WAMP stack) with PHP 8.0+ and MySQL
- Git (optional)
### 2. Clone or download the project
```bash
