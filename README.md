# Digi-Adda E-Commerce Demo

A clean, responsive single-page static e-commerce storefront built with plain HTML, CSS and JavaScript (no frameworks). 

This project demonstrates a mobile-first shopping experience with a product catalog, cart, quick-view modal, persistent cart with localStorage, deals page, and checkout flow with a fake payment gateway.

## 🚀 Live Experience
- `index.html`: product listing + search + cart drawer + quick view
- `deals.html`: flash sale landing page + countdown timer + feature comparison
- `product.html`: product details page with reviews
- `checkout.html`: order summary + billing details + payment modal + success tracker

## 🧩 Features
1. Product catalog with image cards, names, price, and add-to-cart action
2. Live product search in catalog (name + description)
3. Side cart drawer
   - add / increment / decrement quantity
   - remove when quantity reaches 0
   - persistent state via `localStorage` (`myCart` key)
   - total item count and grand total updated automatically
4. Quick View modal for products
   - show photo, price, description
   - add to cart + full details navigation
5. Theme toggle (light/dark) saved as `vibe` in localStorage
6. Product detail page (`product.html?id=<id>`) using URL search parameter
   - product details, specs placeholder, reviews
7. Deals page
   - 5 hour countdown timer (flash sale style)
   - promotional cards and feature comparison
8. Checkout page
   - item list, subtotal, tax (18%), total
   - upsell suggestions (2 random products)
   - fake Razorpay-like modal with tabs (UPI/Card/COD)
   - payment success animation + order tracker + invoice generation
9. Fault tolerance
   - image fallback on load failure
   - empty-cart UI message with action button
   - checkout button disabled when cart empty

## 📁 Project structure
```
index.html
product.html
deals.html
checkout.html
style.css
script.js
README.md
```

## 💻 Setup & run
1. Clone repo
   ```bash
   git clone https://github.com/simar022/E-commerce-DigiAdda.git
   cd E-commerce-DigiAdda
   ```
2. Open `index.html` in your browser
3. Or use simple server (recommended for path stability)
   ```bash
   python3 -m http.server 8000
   # browser: http://localhost:8000
   ```

## 🔧 How to test
- Add multiple products from `index.html` and verify cart counts + totals
- Refresh page and ensure cart persists
- Search for product names/descriptions in header searchfield
- Click Quick View > Add to Bag > verify list changes / checkout enable
- Open `product.html?id=XX` for detail view and nav back
- In `checkout.html`, click Pay Now > simulate payment > confirm success

## 🛠️ Tech
- HTML5 + CSS3
- Vanilla JavaScript (ES6)
- LocalStorage persistence
- Responsive layout + CSS variables
- Client-side routing using URL query params

## ✅ Customization ideas
- Add real ecommerce backend (Firebase / Node/Express API)
- Persist users and sessions (login/register)
- Real payment integration (Stripe/Razorpay)
- Shipping and address form
- Sorting / filtering by category/price
- Better product data (JSON file or API request instead of in-code array)
- Add cart toast notifications
- Add product reviews + ratings CRUD

## 🧾 Cart Storage details
- `cart` object shape: `{ [id]: { id, name, price, imgID, desc, qty }}`
- Save: `localStorage.setItem('myCart', JSON.stringify(cart))`
- Load: `JSON.parse(localStorage.getItem('myCart')) || {}`

## 📝 Notes
- This is a demo and NOT PCI/secure ready for production.
- UI text is styled with Hindi/Bengali slang voice (Bhai, khali, etc.) intentionally for brand tone.

---

Built for learning and prototype evaluation. Enjoy hacking it further!