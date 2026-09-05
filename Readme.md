# Online Food Delivery & E-Commerce Platform

A full-stack food ordering platform with a customer-facing storefront, a cart-to-checkout flow with real payments, and an admin panel for managing the menu and order pipeline.

## Live demo

- **Admin panel:** [food-ecommerce-website.onrender.com](https://food-ecommerce-website.onrender.com)
- **Customer storefront:** [food-ecommerce-website-frontend.onrender.com](https://food-ecommerce-website-frontend.onrender.com)

## What it does

- Customers browse the menu, add items to a cart, and check out with **Stripe** or cash on delivery
- Orders are tracked from placement through status updates (processing → out for delivery → delivered)
- Admins add/remove food items (with image upload via **Cloudinary**) and manage incoming orders from a separate admin app
- Auth is JWT-based, with protected routes for cart and order actions

## Project structure

```
├── backend/    # Express API — auth, food catalog, cart, orders, Stripe
├── frontend/   # Customer-facing storefront (Vite + React)
└── admin/      # Admin panel for menu & order management (Vite + React)
```

## Stack

- **Frontend & Admin** — React 18, Vite, React Router, Axios, React Toastify
- **Backend** — Node.js, Express, MongoDB (Mongoose), JWT auth
- **Payments** — Stripe (card) + cash-on-delivery
- **Media** — Cloudinary (food image uploads)

## API

| Method | Route | Description |
|---|---|---|
| POST | `/api/user/register` | Register a user |
| POST | `/api/user/login` | Log in |
| GET | `/api/food/list` | List food items |
| POST | `/api/food/add` | Add a food item (admin) |
| POST | `/api/food/remove` | Remove a food item (admin) |
| POST | `/api/cart/add` | Add item to cart |
| POST | `/api/cart/remove` | Remove item from cart |
| POST | `/api/cart/get` | Get current cart |
| POST | `/api/order/place` | Place an order via Stripe |
| POST | `/api/order/placecod` | Place an order via cash on delivery |
| POST | `/api/order/verify` | Verify Stripe payment |
| POST | `/api/order/userorders` | Get a user's orders |
| GET | `/api/order/list` | List all orders (admin) |
| POST | `/api/order/status` | Update order status (admin) |

## Getting started

### Backend

```bash
cd backend
npm install
npm run dev
```

Create a `.env` in `backend/` (see `.env.example` for the base vars — `PORT`, `MONGODB_URL`, `JWT_SECRET` — and also set):

```
ALLOWED_ORIGINS=http://localhost:5173,http://localhost:5174
STRIPE_SECRET_KEY=
FRONTEND_URL=
CLOUDINARY_CLOUD_NAME=
CLOUDINARY_API_KEY=
CLOUDINARY_API_SECRET=
```

### Frontend

```bash
cd frontend
npm install
npm run dev
```

### Admin

```bash
cd admin
npm install
npm run dev
```

## Author

Atishay Jain
