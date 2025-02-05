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
        }
        .product {
            background-color: #fff;
            border: 1px solid #ddd;
            border-radius: 4px;
            padding: 20px;
            margin-bottom: 20px;
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
    </style>
</head>
<body>
    <div class="container">
        <div class="product">
            <h2>Moletom de Hip-Hop</h2>
            <img id="productImage" src="image1.jpg" alt="Moletom de Hip-Hop">
            <p>Descrição do moletom de hip-hop.</p>
            <p class="price">R$ 199,90</p>
            <input type="file" id="imageUpload" accept="image/*">
            <button onclick="changeImage()">Alterar Imagem</button>
        </div>
    </div>

    <script>
        function changeImage() {
            const input = document.getElementById('imageUpload');
            const image = document.getElementById('productImage');
            const file = input.files[0];
            const reader = new FileReader();

            reader.onloadend = function () {
                image.src = reader.result;
            };

            if (file) {
                reader.readAsDataURL(file);
            } else {
                image.src = 'image1.jpg';
            }
        }
    </script>
</body
