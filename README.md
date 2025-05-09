<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>lorem.resells</title>
  <link rel="stylesheet" href="styles.css" />
</head>
<body>
  <header>
    <h1>lorem.resells</h1>
    <nav>
      <a href="index.html">Home</a>
      <a href="shop.html">Shop</a>
      <a href="contact.html">Contact</a>
    </nav>
  </header>
  <main>
    <section class="hero">
      <h2>Your Source for Resell Deals</h2>
      <p>Colognes, Shoes, Clothing & Accessories</p>
    </section>
    <section class="categories">
      <div class="category">Colognes</div>
      <div class="category">Shoes</div>
      <div class="category">Clothing</div>
      <div class="category">Accessories</div>
    </section>
  </main>
  <footer>
    <p>&copy; 2025 lorem.resells</p>
  </footer>
</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Shop - lorem.resells</title>
  <link rel="stylesheet" href="styles.css"/>
  <script src="shop.js" defer></script>
</head>
<body>
  <header>
    <h1>lorem.resells</h1>
    <nav>
      <a href="index.html">Home</a>
      <a href="shop.html">Shop</a>
      <a href="contact.html">Contact</a>
    </nav>
  </header>
  <main>
    <h2>Shop All Products</h2>
    <div class="filters">
      <button onclick="filterCategory('all')">All</button>
      <button onclick="filterCategory('Colognes')">Colognes</button>
      <button onclick="filterCategory('Shoes')">Shoes</button>
      <button onclick="filterCategory('Clothing')">Clothing</button>
      <button onclick="filterCategory('Accessories')">Accessories</button>
    </div>
    <div class="products" id="product-list"></div>
  </main>
  <footer>
    <p>&copy; 2025 lorem.resells</p>
  </footer>
</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Contact - lorem.resells</title>
  <link rel="stylesheet" href="styles.css"/>
</head>
<body>
  <header>
    <h1>lorem.resells</h1>
    <nav>
      <a href="index.html">Home</a>
      <a href="shop.html">Shop</a>
      <a href="contact.html">Contact</a>
    </nav>
  </header>
  <main>
    <h2>Contact Us</h2>
    <form>
      <input type="text" placeholder="Your Name" required />
      <input type="email" placeholder="Your Email" required />
      <textarea placeholder="Your Message" required></textarea>
      <button type="submit">Send</button>
    </form>
    <p>Or reach out via Instagram: @lorem.resells</p>
  </main>
  <footer>
    <p>&copy; 2025 lorem.resells</p>
  </footer>
</body>
</html>
body {
  font-family: Arial, sans-serif;
  margin: 0;
  background: #f9f9f9;
  color: #333;
}
header {
  background: #fff;
  padding: 1em;
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-bottom: 1px solid #ccc;
}
nav a {
  margin: 0 1em;
  text-decoration: none;
  color: #333;
}
.hero {
  text-align: center;
  padding: 2em;
  background: #ececec;
}
.categories {
  display: flex;
  justify-content: space-around;
  padding: 1em;
}
.category {
  padding: 1em;
  background: white;
  border: 1px solid #ccc;
  width: 20%;
  text-align: center;
}
.products {
  display: flex;
  flex-wrap: wrap;
  padding: 1em;
}
.product {
  width: 23%;
  margin: 1%;
  padding: 1em;
  background: #fff;
  border: 1px solid #ddd;
}
form {
  display: flex;
  flex-direction: column;
  width: 300px;
  margin: auto;
}
form input, form textarea {
  margin-bottom: 1em;
  padding: 0.5em;
}
button {
  padding: 0.7em;
  background: #333;
  color: white;
  border: none;
  cursor: pointer;
}
footer {
  text-align: center;
  padding: 1em;
  background: #eee;
}
const products = [
  { title: "Chanel Bleu", category: "Colognes", price: "$90" },
  { title: "Nike Air Max", category: "Shoes", price: "$120" },
  { title: "Vintage Jacket", category: "Clothing", price: "$60" },
  { title: "Ray-Ban Sunglasses", category: "Accessories", price: "$80" }
];

function displayProducts(items) {
  const list = document.getElementById('product-list');
  list.innerHTML = '';
  items.forEach(item => {
    const card = document.createElement('div');
    card.className = 'product';
    card.innerHTML = `
      <h3>${item.title}</h3>
      <p>${item.category}</p>
      <p>${item.price}</p>
      <button>Contact to Buy</button>
    `;
    list.appendChild(card);
  });
}

function filterCategory(category) {
  if (category === 'all') {
    displayProducts(products);
  } else {
    displayProducts(products.filter(p => p.category === category));
  }
}

document.addEventListener('DOMContentLoaded', () => displayProducts(products));
