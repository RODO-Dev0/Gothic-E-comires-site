# Gothic-E-comires-site
This is a Gothic Shopping site example made lees in a day solo


# Obscvra Gothic Atelier — Full Site

A complete gothic fashion e-commerce website with full checkout, 5 Iraqi payment methods, and Formspree order backend. No framework, no build step — pure HTML/CSS/JS.

---

## File Tree

```
obscvra/
├── index.html        ← Entire site (self-contained)
└── README.md
```

---

## Features

| Feature | Detail |
|---|---|
| Loading animation | Gothic sigil rings + brand reveal + progress bar |
| Navigation | Scroll-reactive, mobile hamburger, eye cart icon |
| Product grid | 8 products, glass cards with real-time cursor reflection |
| Product panel | Full detail slide-in (right → left), size + qty picker |
| Cart | Eye-icon badge, add/remove, subtotal |
| Checkout | 4-step wizard: Review → Details → Payment → Confirmation |
| Payment methods | ZainCash, FIB, FastPay, IQ Pay, Cash on Delivery |
| Order backend | Formspree — organized email per order |
| Mobile | Swipe-right to close panels, responsive grid |
| Animations | Scroll reveal, marquee band, hover microinteractions |

---

## Setup: Formspree (order emails)

1. Go to [formspree.io](https://formspree.io) and create a free account
2. Click **+ New Form** — name it "Obscvra Orders"
3. Copy your form ID (looks like `xpwzyvpq`)
4. In `index.html`, find this line (~line 480):

```html
<form id="fsForm" action="https://formspree.io/f/YOUR_FORM_ID" method="POST" style="display:none">
```

5. Replace `YOUR_FORM_ID` with your actual ID:

```html
<form id="fsForm" action="https://formspree.io/f/xpwzyvpq" method="POST" style="display:none">
```

Each order email you receive will contain:
- Order ID
- Customer name, phone, email
- City + delivery address
- All items ordered (name, size, qty, price)
- Subtotal, delivery fee, total
- Payment method
- Notes
- Order date/time

---

## Customize

### Products
Edit the `PRODUCTS` array in the `<script>` block. Each product:
```js
{
  id: 1,
  name: "Product Name",
  cat: "Category",
  isNew: true,               // shows "New" badge
  desc: "Short description (card)",
  long: "Full description (panel)",
  price: 420000,             // price in IQD (integer)
  priceDisplay: "420,000 IQD",
  fabric: "Material",
  origin: "Country",
  care: "Care instructions",
  img: "https://...",        // image URL
  sizes: ["XS","S","M","L","XL"]
}
```

### Delivery fee
Change `const DELIVERY = 10000;` (~line 340) to your desired fee in IQD.

### Payment details
Update `PAY_INFO` (~line 270) with your actual wallet numbers/account details.

### Contact info
Update the footer section with your real email, Instagram, and WhatsApp number.

### Colors
All colors are CSS variables at the top of the `<style>` block:
```css
--blood: #7a0000;   /* main accent */
--crimson: #a30000; /* hover state */
--silver: #b5a5cc;  /* secondary text */
--pale: #ede5f5;    /* primary text */
```

---

## Host on GitHub Pages

### Option A — GitHub CLI (fastest)
```bash
cd obscvra
git init
git add .
git commit -m "feat: Obscvra gothic atelier v2"
gh repo create obscvra --public --push --source=.
```
Then: **GitHub repo → Settings → Pages → Branch: main → / (root) → Save**

### Option B — Manual upload
1. Create a new repo on github.com named `obscvra`
2. Upload `index.html` and `README.md`
3. Go to **Settings → Pages → Source: Deploy from branch → main → / (root) → Save**

Your site will be live at:
```
https://YOUR-USERNAME.github.io/obscvra
```

---

## Custom Domain (optional)
1. Buy a domain (e.g. `obscvra.iq` or `obscvra.com`)
2. In GitHub Pages settings, enter your domain under "Custom domain"
3. Add a `CNAME` file in the repo containing just your domain name
4. Point your domain's DNS to GitHub Pages IPs

---

## License
MIT — do whatever you like.
