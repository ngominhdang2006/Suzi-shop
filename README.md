# Suzi-shop
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Suzi Set - Shop</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 30px;
      background-color: #f9f9f9;
    }

    .product {
      border: 1px solid #ddd;
      border-radius: 10px;
      padding: 20px;
      max-width: 350px;
      background: #fff;
    }

    .product h2 {
      margin-top: 0;
    }

    select, button {
      padding: 10px;
      margin-top: 10px;
      width: 100%;
      font-size: 16px;
    }

    button {
      background-color: #4CAF50;
      color: white;
      border: none;
      cursor: pointer;
      border-radius: 5px;
    }

    button:hover {
      background-color: #45a049;
    }

    .cart {
      margin-top: 30px;
      padding: 20px;
      background: #fff3cd;
      border: 1px solid #ffeeba;
      border-radius: 10px;
      max-width: 350px;
    }
  </style>
</head>
<body>

  <div class="product">
    <h2>Suzi Set</h2>
    <p><strong>Price:</strong> $29.99</p>
    <label for="size">Choose a size:</label>
    <select id="size">
      <option value="">-- Select size --</option>
      <option value="S">S</option>
      <option value="M">M</option>
      <option value="L">L</option>
      <option value="XL">XL</option>
    </select>
    <button onclick="addToCart()">Add to Cart</button>
  </div>

  <div class="cart" id="cart">
    <h3>🛒 Shopping Cart</h3>
    <ul id="cart-items">
      <li>No items in cart.</li>
    </ul>
  </div>

  <script>
    const cartItems = [];

    function addToCart() {
      const size = document.getElementById('size').value;
      const cartList = document.getElementById('cart-items');

      if (!size) {
        alert('Please select a size!');
        return;
      }

      const item = `Suzi Set (Size: ${size})`;
      cartItems.push(item);

      // Update cart
      cartList.innerHTML = '';
      cartItems.forEach(i => {
        const li = document.createElement('li');
        li.textContent = i;
        cartList.appendChild(li);
      });
    }
  </script>

</body>
</html>
