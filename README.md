# 🍲 CraveBite - Modern Web Food Ordering Application

[![License: MIT](https://img.shields.io/badge/License-MIT-orange.svg)](https://opensource.org/licenses/MIT)
[![Stack](https://img.shields.io/badge/Tech--Stack-HTML5%20%7C%20CSS3%20%7C%20JS%20%7C%20SQLite-blue)](https://github.com)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)

**CraveBite** is a fast, lightweight, and interactive single-page food ordering web application designed to bring a seamless restaurant browsing and checkout experience directly to users' web browsers. Built using pure vanilla web tech combined with an **in-browser SQLite relational database** powered by WebAssembly (`sql.js`), CraveBite manages users, delivery addresses, shopping carts, menu catalogs, and complete order histories entirely client-side without relying on an external backend API server!

---

## 📌 Problem Statement & Solution

* **The Problem**: Traditional full-stack food delivery applications depend heavily on backend database connections and server environments, making initial setup, local testing, and offline demonstration slow and complex.
* **The CraveBite Solution**: CraveBite runs a full relational database instance inside the browser runtime using `sql.js` (SQLite WASM). Data persists smoothly across browser sessions via `localStorage`, giving you real SQL querying capabilities directly in the browser with zero server overhead.

---

## 🌟 Key Features & Capabilities

- 🍕 **Rich Food Menu Catalog**: Browse dishes across multiple food categories including *Meals, Starters, Snacks, Beverages, and Desserts*.
- 🔍 **Real-Time Search & Diet Filters**: Instant live filtering by dish name or description alongside dietary toggles (e.g., *Veg Only*).
- 🛒 **Dynamic Shopping Cart**: Interactive cart overlay featuring live price calculations (Subtotal, GST, Delivery Fees) and real-time quantity updates.
- 💳 **Integrated Multi-Channel Checkout**: Realistic payment portal interface supporting Credit/Debit Cards, UPI, Net Banking, and Cash on Delivery (COD).
- 📍 **Saved Address Manager**: Store and select multiple shipping addresses saved inside the client-side SQLite database.
- 📜 **Order Tracking & History Logs**: View detailed past order summaries, status indicators, and full transaction details.
- 👤 **User Authentication**: Complete client-side sign-up and login workflow linked with user-specific sessions.
- 💾 **Client-side SQLite Database**: Fully functional SQLite relational database compiled to WebAssembly running within browser memory with binary export/restoration capabilities.

---

## 🏗️ Technical Architecture & Stack

| Layer | Technology | Functionality & Usage |
| :--- | :--- | :--- |
| **Frontend UI** | HTML5, CSS3, Vanilla JS | Clean responsive UI built with modern CSS Grid/Flexbox and DOM manipulation |
| **Database Engine** | SQLite (`sql.js` WebAssembly) | Client-side relational engine running queries directly in browser memory |
| **Data Persistence** | `localStorage` + Base64 Encoding | Serializes SQLite database binary into Base64 for persistent browser storage |
| **Design & Typography** | Boxicons, Google Fonts | *DM Sans* and *Playfair Display* fonts paired with lightweight SVG icons |

---

## 📊 Database Schema Design

CraveBite utilizes a complete relational schema composed of 8 structured tables:

- **`users`**: Contains user accounts (`id`, `email`, `password_hash`, `full_name`, `created_at`).
- **`addresses`**: Stores delivery addresses associated with specific users (`id`, `user_id`, `street`, `city`, `zip_code`).
- **`menu_items`**: Menu catalog storage (`id`, `name`, `category`, `price`, `is_veg`, `rating`, `image`, `description`).
- **`orders`**: Master order transaction records (`id`, `user_id`, `subtotal`, `gst`, `delivery_fee`, `total_amount`, `payment_method`, `created_at`).
- **`order_items`**: Mapping table connecting specific ordered dishes and quantities to master orders.
- **`delivery_info`**: Tracks live delivery status updates and driver details for placed orders.
- **`reviews`**: Stores user ratings and textual feedback for food items.
- **`cart`**: Maintains active persistent cart state across sessions for each user.

---

## 📁 Repository Structure

```text
cravebite/
│
├── index.html         # Primary application layout, menu, cart, modals, and navigation
├── login.html         # User authentication page for login and registration flows
├── styles.css         # Complete styling rules, dark mode palette, responsive layouts
├── script.js          # Core application logic, event listeners, state & view updates
├── db.js              # SQLite WASM initialization, schema setup, sample data seeding
├── dbHelper.js        # Asynchronous SQL query helper functions (Users, Orders, Cart, Addresses)
├── data.js            # Default menu categories and food dish dataset
└── README.md          # Comprehensive project documentation
