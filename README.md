# Easy-Pay-
A Community Electricity Billing Application based on MVC framework. The application automatically creates household enumeration codes, assign code numbers to households based on house type (Basic, Bungalow, or Duplex). Users login and use different payment methods to remit their payment ater generating invoices. They can view  and track a

# Easy Pay - Community Electricity Billing Platform

![Easy Pay Logo](public/images/logo.png)

Easy Pay is a **digital platform for community electricity payments**, allowing households to register, pay bills online, and track payments in real time. It automates billing, supports multiple payment channels, and provides administrators with real-time dashboards and audit trails.

---

## Table of Contents

- [Features](#features)  
- [Installation](#installation)  
- [Usage](#usage)  
- [Routes](#routes)  
- [Database Schema](#database-schema)  
- [Contributing](#contributing)  
- [License](#license)  

---

## Features

- Automated monthly billing for registered households  
- Unique household ID system  
- Multiple payment channels  
- Real-time analytics dashboard  
- Payment reconciliation and audit trails  
- User authentication (login/register)  
- Feedback & complaint submission  
- Testimonials carousel on homepage  

---

## Installation

### Prerequisites

- PHP >= 8.1  
- Composer  
- MySQL or MariaDB  
- Node.js & npm (for Laravel Mix/Assets)  

### Steps

1. Clone the repository:

```bash
git clone https://github.com/yourusername/easypay.git
cd easypay

2. Install dependencies:

composer install
npm install
npm run dev

3. Copy .env.example to .env and configure database:

cp .env.example .env
php artisan key:generate


4. Setup Database connections

 DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=easypay
DB_USERNAME=root
DB_PASSWORD=

5. Run Migrations
php artisan migrate


6. Serve the application
php artisan serve






7. Access the App on a browser (localhost)
http://127.0.0.1:8000

8. Route Overview
### Routes Overview

| Route | Method | Description |
|-------|--------|-------------|
| `/` | GET | Home Page |
| `/register-household` | GET/POST | Create new household |
| `/login` | GET/POST | User login |
| `/paybill` | GET/POST | Make payment using household ID |
| `/payments` | GET | View all payments (admin) |
| `/feedback` | POST | Submit feedback/complaint |


9. Database Schema
### Household Table

| Field | Type | Description |
|-------|------|-------------|
| id | bigint | Primary key |
| unique_id | string | Unique household code |
| household_name | string | Name of household |
| code_no | string | Household code number |
| address | string | Street address |
| village | string | Village name |
| town | string | Town name |
| lga | string | Local government area |
| contact_phone | string | Contact phone number |
| contact_email | string | Contact email |
| household_type | enum | Basic, Bungalow, Duplex |
| created_at | timestamp | Timestamp |
| updated_at | timestamp | Timestamp |

### Payments Table

| Field | Type | Description |
|-------|------|-------------|
| id | bigint | Primary key |
| household_id | bigint | Foreign key to households |
| amount | integer | Payment amount |
| status | string | Paid / Pending |
| created_at | timestamp | Timestamp |
| updated_at | timestamp | Timestamp |




10. License

This project is licensed under the MIT License - see the LICENSE
 file for details.
