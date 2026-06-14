# HeatSeekers Collective — Setup Guide
Everything you need to go live. Do these in order.

---

## STEP 1 — Get the site live on Vercel (Free, 10 minutes)

1. Go to github.com and create a free account
2. Create a new repository called "heatseekers"
3. Upload index.html and vercel.json to that repository
4. Go to vercel.com and sign up with your GitHub account
5. Click "Add New Project" → select your "heatseekers" repo
6. Click Deploy — your site is live at a .vercel.app URL instantly

---

## STEP 2 — Get a real domain (~15 minutes)

1. Go to namecheap.com
2. Search "heatseekerscollective.com" (or .shop, .co)
3. Buy it — roughly $14/year
4. In Vercel: go to your project → Settings → Domains
5. Add your domain and follow the instructions to point it

---

## STEP 3 — Add your products

Open index.html in any text editor (Notepad works, VS Code is better — free at code.visualstudio.com)

Find the PRODUCTS array (search for "PRODUCTS = [")

For each product, fill in:
- name: the artist/brand name
- sub: the specific item description  
- price: your asking price as a number
- era: "90s" or "Y2K"
- cat: "Shirts", "Hoodies", "Bottoms", or "Outerwear"
- emoji: a placeholder until you add photos
- photo: the path to your photo file (see Step 4)
- sizes: list of available sizes like ["S", "M", "L"]
- soldSizes: sizes that are sold, like ["S"] — leave [] if all available
- desc: your description of the piece
- measurements: chest, length, sleeve, condition

---

## STEP 4 — Add product photos

1. Create a folder called "images" inside your heatseekers folder
2. Name your photos clearly: lil-peep-hoodie.jpg, godflesh-ls.jpg etc.
3. In each product, change: photo: null  →  photo: '/images/your-photo.jpg'
4. Upload the images folder to GitHub alongside index.html

Photo tips:
- Shoot on a flat surface or hang on a wall, neutral background
- Good lighting — near a window works great
- Shoot front, back, tags, any details
- Use the first/best shot as the main product photo

---

## STEP 5 — Connect Shopify for checkout ($5/month)

1. Go to shopify.com/starter and sign up for the Starter plan
2. Add each of your products in the Shopify dashboard
3. Go to Sales Channels → Buy Button in Shopify
4. Create a buy button for each product
5. Copy the embed code
6. In index.html, find "SHOPIFY BUY BUTTON FOR PRODUCT ID: X"
7. Replace the fallback button with your Shopify embed code

---

## STEP 6 — Connect Instagram widget

1. Go to lightwidget.com
2. Click Create Widget → log in with @Heatseekers_collective
3. Settings: 3 columns, square crop, no border, no padding
4. Copy the embed code
5. In index.html, find "<!-- INSTAGRAM WIDGET — REPLACE THIS BLOCK -->"
6. Replace the ig-placeholder-grid div with your LightWidget code
7. Do this in BOTH places (home page and archive page)

---

## STEP 7 — Email list

The simplest free option is Formspree:
1. Go to formspree.io and create a free account
2. Create a new form, copy your form endpoint URL
3. In index.html, find the subEmail() function
4. Replace the comment with: fetch('YOUR_FORMSPREE_URL', { method:'POST', body: JSON.stringify({email: v}), headers:{'Content-Type':'application/json'} })

---

## EVERY MONTH — Drop update checklist

Before each drop:
[ ] Update DROP_DATE in index.html to your new drop date
[ ] Update DROP_NAME to match (e.g. "August Drop 038")
[ ] Move sold items from PRODUCTS array to ARCHIVE array
[ ] Add new products to PRODUCTS array
[ ] Add new photos to /images/ folder
[ ] Upload all changes to GitHub (Vercel auto-deploys in 30 seconds)

---

## File structure when done

heatseekers/
  index.html        ← the whole website
  vercel.json       ← Vercel config (don't touch)
  images/
    lil-peep-hoodie.jpg
    godflesh-ls.jpg
    your-photos-here.jpg

---

## Questions?

Every section in index.html has comments that explain exactly what to change.
Search for "CHANGE THIS", "UPDATE THIS", or "PASTE" to find all the spots.
