<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DarLig - Tienda</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background: linear-gradient(to right, #6a0dad, #ff69b4);
            color: white;
            text-align: center;
            margin: 0;
            padding: 20px;
        }
        .container {
            max-width: 900px;
            margin: auto;
            background: rgba(0, 0, 0, 0.8);
            padding: 20px;
            border-radius: 10px;
        }
        .product {
            display: inline-block;
            width: 250px;
            margin: 15px;
            padding: 10px;
            background: white;
            color: black;
            border-radius: 8px;
        }
        .product img {
            width: 100%;
            height: 200px;
            object-fit: cover;
            border-radius: 5px;
        }
        .price {
            font-size: 18px;
            font-weight: bold;
            color: #6a0dad;
        }
        .status {
            font-size: 14px;
            font-weight: bold;
        }
        .available { color: green; }
        .out-of-stock { color: red; }
    </style>
</head>
<body>
    <div class="container">
        <h1>Bienvenido a DarLig</h1>
        <p>Explora nuestros productos exclusivos.</p>

        <div id="products"></div>
    </div>

    <script>
        const products = [
            { name: "Caja de cocholates, price: "$17.000", image: "https://via.placeholder.com/250", available: true },
            { name: "Happy nappers", price: "$30.000", image: "https://via.placeholder.com/250", available: false },
            { name: "vasos desechables ", price: "$20.000", image: "https://via.placeholder.com/250", available: true }
        ];

        const productContainer = document.getElementById("products");

        products.forEach(product => {
            const productDiv = document.createElement("div");
            productDiv.classList.add("product");
            productDiv.innerHTML = `
                <img src="${product.image}" alt="${product.name}">
                <h3>${product.name}</h3>
                <p class="price">${product.price}</p>
                <p class="status ${product.available ? 'available' : 'out-of-stock'}">
                    ${product.available ? "Disponible" : "Agotado"}
                </p>
            `;
            productContainer.appendChild(productDiv);
        });
    </script>
</body>
</html>
