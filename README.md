<!DOCTYPE html>
<html lang="pt-br">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Lumèia Acessórios</title>

<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@500;700&family=Montserrat:wght@300;400;500&display=swap" rel="stylesheet">

<style>
body{
margin:0;
font-family:'Montserrat',sans-serif;
background:#F5F1E8;
color:#111;
}

header{
background:#C9C2AD;
text-align:center;
padding:30px;
}

header h1{
font-family:'Playfair Display',serif;
font-size:42px;
margin:0;
}

nav{
background:#A8B08C;
text-align:center;
padding:15px;
}

nav a{
text-decoration:none;
color:#111;
margin:0 15px;
font-weight:500;
}

.produtos{
padding:50px 20px;
text-align:center;
}

.grid{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(250px,1fr));
gap:30px;
}

.card{
background:white;
border-radius:18px;
padding:15px;
box-shadow:0 10px 25px rgba(0,0,0,0.08);
transition:0.3s;
}

.card:hover{
transform:translateY(-5px);
}

.imagem-container{
overflow:hidden;
border-radius:12px;
}

.card img{
width:100%;
transition:0.5s;
cursor:pointer;
}

.card img:hover{
transform:scale(1.15);
}

.card h3{
font-family:'Playfair Display',serif;
margin:15px 0 5px;
}

.preco{
color:#7A4E2A;
font-weight:bold;
margin-bottom:15px;
}

button{
background:#E4B83F;
border:none;
padding:10px 18px;
border-radius:8px;
cursor:pointer;
font-weight:500;
margin:5px;
}

.carrinho{
position:fixed;
top:20px;
right:20px;
background:#E4B83F;
padding:10px 15px;
border-radius:50px;
cursor:pointer;
}

footer{
background:#C9C2AD;
text-align:center;
padding:20px;
margin-top:50px;
}

/* MODAL */
#modal{
display:none;
position:fixed;
inset:0;
background:rgba(0,0,0,0.8);
justify-content:center;
align-items:center;
}

#modal img{
max-width:90%;
max-height:90%;
border-radius:15px;
}
</style>
</head>

<body>

<div class="carrinho" onclick="abrirCarrinho()">
🛒 Carrinho (<span id="contador">0</span>)
</div>

<header>
<h1>LUMÈIA</h1>
<p>Laços que encantam 🌻</p>
</header>

<nav>
<a href="#">Início</a>
<a href="#">Laços</a>
<a href="#">Contato</a>
</nav>

<section class="produtos">
<h2>Nossos Laços</h2>

<div class="grid">

<div class="card">
<div class="imagem-container">
<img src="imagem1.jpg" onclick="abrirImagem(this.src)">
</div>
<h3>Laço Girassol</h3>
<p class="preco">R$ 29,90</p>
<button onclick="adicionarCarrinho('Laço Girassol - R$29,90')">Adicionar</button>
</div>

<div class="card">
<div class="imagem-container">
<img src="imagem2.jpg" onclick="abrirImagem(this.src)">
</div>
<h3>Laço Delicado</h3>
<p class="preco">R$ 24,90</p>
<button onclick="adicionarCarrinho('Laço Delicado - R$24,90')">Adicionar</button>
</div>

<div class="card">
<div class="imagem-container">
<img src="imagem3.jpg" onclick="abrirImagem(this.src)">
</div>
<h3>Laço Natural</h3>
<p class="preco">R$ 32,90</p>
<button onclick="adicionarCarrinho('Laço Natural - R$32,90')">Adicionar</button>
</div>

</div>
</section>

<footer>
© 2026 Lumèia - Todos os direitos reservados
</footer>

<!-- MODAL IMAGEM -->
<div id="modal" onclick="fecharImagem()">
<img id="imagemAmpliada">
</div>

<script>
let carrinho=[];

function adicionarCarrinho(item){
carrinho.push(item);
document.getElementById("contador").innerText=carrinho.length;
}

function abrirCarrinho(){
let mensagem="Olá! Gostaria de comprar:%0A";
carrinho.forEach(item=>{
mensagem+=item+"%0A";
});
window.open("https://wa.me/55SEUNUMEROAQUI?text="+mensagem);
}

function abrirImagem(src){
document.getElementById("modal").style.display="flex";
document.getElementById("imagemAmpliada").src=src;
}

function fecharImagem(){
document.getElementById("modal").style.display="none";
}
</script>

</body>
</html>
