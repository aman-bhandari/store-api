# Store API (NodeJs - Express - MongoDB)

A simple REST API for store. This is API products includes show list of the products, sorting, filtering, search for product name and custom pagination.

## Usage

## Route API

| **HTTP Method** |    **Route**    |       **Result**       |
| :-------------: | :-------------: | :--------------------: |
|       GET       | api/v1/products | Get a list of products |

### **1. products.json**

This file has 23 product data.

### **2. populate.js**

**WARNING:** If using this file first **delete** all documents in mongo and after that, Create products data. (products.json).

---

## Options

You can set some request header for a customized response.

### Request Headers

#### - featured

You can set featured True or false for customized products.

**example:**

    http://localhost:3000/api/v1/products?featured=false

#### - company

You can sellect company name.

**example:**

    http://localhost:3000/api/v1/products?featured=false&company=liddy

#### - name

You can search on the product name. (The code logic for searching product names uses a regex and does not case sensitive.)

**example:**

    http://localhost:3000/api/v1/products?name=Table

#### - sort

You can sort price, rating, created_at, name, and...

Also, you can multiple sorting.

**example:** sort by increase price

    http://localhost:3000/api/v1/products?sort=price

**example:** sort by decrease price

    http://localhost:3000/api/v1/products?sort=-price

**example:** sort by multiple

    http://localhost:3000/api/v1/products?sort=price,-rating

#### - fields

You can select fields in response.

**example:**

    http://localhost:3000/api/v1/products?fields=name,rating,price

#### - numericFilters

You can filter price and rating products.

**example:**

    http://localhost:3000/api/v1/products?numericFilters=price>30,rating>=3

### pagination

#### - page

You can go to another page.

**example:**

    http://localhost:3000/api/v1/products?page=2

#### - limit

You can change the limit of the number of products on the list. (default = 10 )

**example:**

    http://localhost:3000/api/v1/products?limit=5
