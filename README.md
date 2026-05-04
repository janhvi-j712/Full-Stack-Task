# Book Store & Inventory Management API

## Setup

1. Copy `.env.example` to `.env` and update:
   ```
   MONGO_URI=mongodb://localhost:27017/bookstore
   PORT=3000
   ```
   (Start MongoDB locally)

2. Install dependencies:
   ```
   npm install
   ```

3. Run development server:
   ```
   npm run dev
   ```

Server runs on `http://localhost:3000`

## Postman Test Instructions

### Book Store APIs (Base: http://localhost:3000/api/books)

| Method | Endpoint | Description | Body Example |
|--------|----------|-------------|--------------|
| POST | `/api/books` | Add book | `{"title":"Test Book","author":"Author","price":19.99,"category":"Fiction","stock":10}` |
| GET | `/api/books` | Get all books | - |
| GET | `/api/books/:id` | Get book by ID | - |
| PUT | `/api/books/:id` | Update book | `{"price":25.00}` |
| DELETE | `/api/books/:id` | Delete book | - |

**Validation**: Title required, price > 0.

### Inventory APIs (Base: http://localhost:3000/api/products)

| Method | Endpoint | Description | Body Example |
|--------|----------|-------------|--------------|
| POST | `/api/products` | Add product | `{"productName":"Laptop","quantity":5,"price":999,"supplier":"TechCorp","inStock":true}` |
| GET | `/api/products` | Get all | - |
| GET | `/api/products?lowStock=true` | Low stock (<10) | - |
| GET | `/api/products?search=laptop` | Search by name | - |
| GET | `/api/products/:id` | Get by ID | - |
| PUT | `/api/products/:id` | Update | `{"quantity":10,"price":899}` |
| DELETE | `/api/products/:id` | Delete | - |

**Validation**: quantity >=0, price required.

## Error Handling
All APIs return JSON: `{success: boolean, data/message: ...}` with proper status codes (200,201,400,404,500).

Test all endpoints in Postman!
