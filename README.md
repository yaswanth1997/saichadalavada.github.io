# AWS

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Awesome Products</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }
        #products-container {
            display: flex;
            flex-wrap: wrap;
        }
        .product {
            border: 1px solid #ddd;
            padding: 10px;
            margin: 10px;
            width: 200px;
        }
    </style>
</head>
<body>

<h1>Welcome to Our Awesome Products Page!</h1>

<div id="products-container"></div>

<script>
    // Fetch products from AWS API (replace URL with your actual API endpoint)
    fetch('https://your-aws-api-endpoint.com/products')
        .then(response => response.json())
        .then(products => {
            const productsContainer = document.getElementById('products-container');

            products.forEach(product => {
                const productElement = document.createElement('div');
                productElement.className = 'product';
                productElement.innerHTML = `
                    <h3>${product.name}</h3>
                    <p>${product.description}</p>
                    <p>Price: $${product.price}</p>
                `;
                productsContainer.appendChild(productElement);
            });
        })
        .catch(error => {
            console.error('Error fetching products:', error);
        });
</script>

</body>
</html>




