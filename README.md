# lusca
oi, meu nome é Lucas, tenho 16 anos, gosto de futebol, tenho amigos "muito legais", moro com meus pais e meus dois irmâos, tenho uma namorada e meu ídolo é o Neymar
/venda-site
|-- /public
|   |-- /css
|   |   |-- styles.css
|   |-- /js
|   |   |-- script.js
|-- /views
|   |-- index.ejs
|-- server.js
|-- package.json

const express = require('express');
const app = express();

app.set('view engine', 'ejs');
app.use(express.static('public'));

const produtos = [
    { id: 1, nome: 'Produto A', preco: 100 },
    { id: 2, nome: 'Produto B', preco: 200 },
    { id: 3, nome: 'Produto C', preco: 300 }
];

app.get('/', (req, res) => {
    res.render('index', { produtos });
});

const PORT = process.env.PORT || 3000;
app.listen(PORT, () => {
    console.log(`Servidor rodando na porta ${PORT}`);
});

<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Site de Vendas</title>
    <link rel="stylesheet" href="/css/styles.css">
</head>
<body>
    <header>
        <h1>Loja Online</h1>
    </header>

    <main>
        <section class="produtos">
            <% produtos.forEach(produto => { %>
                <div class="produto">
                    <h2><%= produto.nome %></h2>
                    <p>Preço: R$ <%= produto.preco %></p>
                    <button onclick="adicionarAoCarrinho(<%= produto.id %>)">Adicionar ao Carrinho</button>
                </div>
            <% }); %>
        </section>
    </main>

    <script src="/js/script.js"></script>
</body>
</html>

body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    background-color: #f4f4f4;
}

header {
    background-color: #333;
    color: white;
    padding: 1rem;
    text-align: center;
}

.produtos {
    display: flex;
    justify-content: space-around;
    margin: 2rem;
}

.produto {
    background-color: white;
    padding: 1rem;
    border: 1px solid #ddd;
    width: 200px;
    text-align: center;
}

button {
    background-color: #28a745;
    color: white;
    padding: 0.5rem;
    border: none;
    cursor: pointer;
}

button:hover {
    background-color: #218838;
}

function adicionarAoCarrinho(produtoId) {
    alert(`Produto ${produtoId} adicionado ao carrinho!`);
}

npm install

npm start
