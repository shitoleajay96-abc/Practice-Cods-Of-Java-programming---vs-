# Restaurant Billing & Online Ordering System

A practice project that models how a restaurant can let customers order and pay from their phone, without going to the counter.

> **Status:** Frontend prototype (HTML, CSS, JavaScript). Java Spring Boot backend is planned next.

## Files

| File | Description |
|------|-------------|
| `bill.html` | Receipt-style bill generator. Add items, quantity and rate; subtotal, SGST, CGST and grand total are calculated live. Print-friendly. |
| `order.html` | Customer ordering flow: choose Dine-in or Parcel, select food, view bill, pay, and track order status. |

## Features

- Dine-in (with table number) and Parcel modes
- Menu with categories and add / remove quantity
- Automatic bill calculation (SubTotal + SGST 2.5% + CGST 2.5%)
- Payment method selection (UPI, Card, Net Banking) - simulated
- Order tracking: Payment received, Preparing, Ready, Served / Pickup
- Mobile-friendly layout, dark mode, print styles

## Concepts Used

- **HTML:** forms, tables, semantic structure, viewport meta tag
- **CSS:** Flexbox, CSS variables, media queries (dark mode, print), fixed bottom bar
- **JavaScript:** state object, arrays and objects, `map` / `filter` / `reduce`, DOM manipulation, events, `setInterval`, input escaping to prevent HTML injection

## Billing Logic

```
amount      = quantity x rate
subtotal    = sum of all amounts
tax         = subtotal x 2.5 / 100      (applied as SGST and CGST)
total       = subtotal + 2 x tax
grand total = round(total)
```

## Limitations (Demo Only)

- Payment is simulated; no real money is processed
- Order status advances automatically; there is no kitchen screen yet
- Data is not saved after page refresh (no database)
- Calculations run in the browser; a real system must calculate on the server

## Planned: Real Backend (Java)

- [ ] Spring Boot REST APIs for menu, orders and bill calculation
- [ ] MySQL database (`menu_items`, `orders`, `order_items`)
- [ ] Payment gateway integration (e.g. Razorpay) with server-side verification
- [ ] Kitchen dashboard to update order status live
- [ ] Unique QR code for each table

## How to Run

Download the files and open `order.html` or `bill.html` in any browser. No installation needed.
