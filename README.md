<!DOCTYPE html>
<html lang="pt">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Loja de Roupas de Hip-Hop</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
            margin: 0;
            padding: 0;
        }
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
        }
        .product {
            background-color: #fff;
            border: 1px solid #ddd;
            border-radius: 4px;
            padding: 20px;
            width: calc(33.333% - 40px);
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        }
        .product img {
            max-width: 100%;
            height: auto;
            border-radius: 4px;
        }
        .product h2 {
            font-size: 24px;
            margin: 0 0 10px;
        }
        .product p {
            font-size: 16px;
            margin: 0 0 10px;
        }
        .product .price {
            font-size: 20px;
            color: #e60000;
        }
        .product input[type="file"] {
            display: none;
        }
        .product label {
            background-color: #007bff;
            color: #fff;
            padding: 10px;
            border-radius: 4px;
            cursor: pointer;
            display: inline-block;
            margin-top: 10px;
        }
    </style>
</head>
<body>
    <div class="container" id="productContainer">
        <!-- Os produtos serão gerados dinamicamente aqui -->
    </div>

    <script>
        const products = [
            { name: 'Moletom de Hip-Hop 1', price: 'R$ 199,90', image: 'image1.jpg' },
            { name: 'Moletom de Hip-Hop 2', price: 'R$ 199,90', image: 'image2.jpg' },
            { name: 'Moletom de Hip-Hop 3', price: 'R$ 199,90', image: 'image3.jpg' },
            // Adicione mais produtos conforme necessário até 15
        ];

        const productContainer = document.getElementById('productContainer');

        products.forEach((product, index) => {
            const productElement = document.createElement('div');
            productElement.className = 'product';
            productElement.innerHTML = `
                <h2>${product.name}</h2>
                <img id="productImage${index}" src="${product.image}" alt="${product.name}">
                <p>Descrição do ${product.name}.</p>
                <p class="price">${product.price}</p>
                <input type="file" id="imageUpload${index}" accept="image/*" onchange="changeImage(${index})">
                <label for="imageUpload${index}">Alterar Imagem</label>
            `;
            productContainer.appendChild(productElement);
        });

        function changeImage(index) {
            const input = document.getElementById(`imageUpload${index}`);
            const image = document.getElementById(`productImage${index}`);
            const file = input.files[0];
            const reader = new FileReader();

            reader.onloadend = function () {
                image.src = reader.result;
            };

            if (file) {
                reader.readAsDataURL(file);
            }
        }
    </script>
</body>
</html>


