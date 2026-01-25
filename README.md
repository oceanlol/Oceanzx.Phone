<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Oceanzx Adopt Me Shop</title>
<meta name="description" content="Oceanzx Adopt Me Shop – Fast delivery, trusted trades, instant Discord checkout.">

<style>
:root{
  --accent:#0a84ff;
  --rare:#8A2BE2;
  --epic:#FF69B4;
  --legendary:#FFD700;
  --bg:#0b0b0b;
  --card:#1c1c1c;
  --text:#ffffff;
  --trust:#00ff99;
}
*{box-sizing:border-box;margin:0;padding:0;font-family:Segoe UI,Arial,sans-serif;}

/* BODY */
body{
  background:var(--bg);
  color:var(--text);
  overflow-x:hidden;
  scroll-behavior:smooth;
  padding-bottom:80px; /* space for cart button */
}

/* HEADER */
header{
  text-align:center;
  padding:30px 15px;
  background:linear-gradient(180deg,#111,#000);
}
header h1{
  font-size:2rem;
  color:var(--accent);
  text-shadow:0 0 8px #0a84ff;
}
header p{
  color:#aaa;
  font-size:1rem;
  margin-top:6px;
}

/* TRUST BAR */
.trust{
  background:linear-gradient(90deg,#00ff99,#00bfff);
  text-align:center;
  padding:10px 0;
  font-weight:bold;
  border-radius:12px;
  margin:10px 15px;
  font-size:.85rem;
  box-shadow:0 0 20px rgba(0,255,153,.3);
}

/* CONTAINER */
.container{
  max-width:500px; /* mobile-friendly width */
  margin:15px auto;
  padding:15px;
  background:#121212;
  border-radius:20px;
  box-shadow:0 0 30px rgba(10,132,255,.15);
}

/* SECTION HEADINGS */
.container h2{
  text-align:center;
  font-size:1.5rem;
  margin-bottom:12px;
  position:relative;
}
.container h2::after{
  content:"";
  display:block;
  width:60px;
  height:3px;
  background:var(--accent);
  margin:6px auto;
  border-radius:2px;
}

/* GRID - vertical layout */
.grid{
  display:flex;
  flex-direction:column;
  gap:15px;
}

/* CARD */
.card{
  background:linear-gradient(180deg,var(--card),#121212);
  border-radius:18px;
  padding:12px;
  text-align:center;
  transition:.35s;
  position:relative;
  overflow:hidden;
  cursor:pointer;
}
.card:hover{
  transform:translateY(-4px);
  box-shadow:0 0 20px rgba(10,132,255,.3);
}
.card img{
  width:100%;
  max-width:200px;
  height:auto;
  object-fit:cover;
  border-radius:14px;
  transition:transform 0.3s;
  margin:0 auto;
}
.card:hover img{
  transform:scale(1.05);
}
.card h3{
  font-size:1.1rem;
  margin:6px 0;
}
.price{
  color:#ccc;
  font-weight:bold;
  margin-top:4px;
}
.stock{
  color:#ff4d4d;
  font-size:.75rem;
  margin-top:2px;
}
.only-one{animation:flash .8s infinite}
@keyframes flash{0%,100%{opacity:1}50%{opacity:.3}}

/* RARITY */
.card.rare img{box-shadow:0 0 10px var(--rare);}
.card.epic img{box-shadow:0 0 10px var(--epic);}
.card.legendary img{box-shadow:0 0 10px var(--legendary);}

/* BUTTON */
.btn{
  background:linear-gradient(180deg,var(--accent),#0066cc);
  border:none;
  padding:8px 14px;
  border-radius:14px;
  color:white;
  font-weight:bold;
  cursor:pointer;
  margin-top:6px;
  transition:.3s;
}
.btn:hover{transform:scale(1.05);}
.btn:disabled{background:#444;cursor:not-allowed;}

/* CART BUTTON */
#cart-btn{
  position:fixed;
  bottom:15px;
  right:15px;
  background:var(--accent);
  width:60px;
  height:60px;
  border-radius:50%;
  color:#000;
  font-size:1.2rem;
  display:flex;
  align-items:center;
  justify-content:center;
  cursor:pointer;
  box-shadow:0 0 20px rgba(10,132,255,.5);
  z-index:1000;
}
#cart-btn span{
  position:absolute;
  top:6px;
  right:6px;
  background:red;
  color:white;
  font-size:.7rem;
  width:18px;
  height:18px;
  border-radius:50%;
  display:flex;
  align-items:center;
  justify-content:center;
}

/* CART PANEL */
#cart-panel{
  position:fixed;
  bottom:0;
  left:0;
  width:100%;
  max-height:70%;
  background:#121212;
  border-top-left-radius:20px;
  border-top-right-radius:20px;
  box-shadow:0 -5px 30px rgba(10,132,255,.3);
  overflow-y:auto;
  padding:15px;
  transform:translateY(100%);
  transition:transform .3s ease-in-out;
  z-index:999;
}
#cart-panel.open{
  transform:translateY(0%);
}
.cart-item{
  display:flex;
  justify-content:space-between;
  margin:6px 0;
  font-size:.9rem;
}
.cart-item span:first-child{
  color:red;
  cursor:pointer;
}
.cart-total{
  margin-top:10px;
  font-weight:bold;
  text-align:right;
}

/* MOBILE ADJUSTMENTS */
@media(max-width:500px){
  .container{padding:10px;margin:10px;}
  .card img{max-width:100%;}
}
</style>
</head>
<body>

<header>
  <h1>Oceanzx Adopt Me Shop</h1>
  <p>Fast delivery • Trusted trades • DM before payment</p>
</header>

<div class="trust">✔ Instant Delivery • ✔ Trusted Trades • ✔ Discord Support</div>

<div class="container">
  <h2>🥚 Eggs Section 🥚</h2>
  <div class="grid" id="eggs-grid"></div>

  <h2>🔥 Pets Section 🔥</h2>
  <div class="grid" id="pets-grid"></div>
</div>

<!-- Cart Button -->
<div id="cart-btn">🛒 <span id="cart-count">0</span></div>

<!-- Cart Panel -->
<div id="cart-panel">
  <h3>🛒 Cart</h3>
  <div id="cart-items"></div>
  <div class="cart-total">Total: $<span id="total">0.00</span></div>
  <button class="btn" onclick="checkout()">Checkout</button>
</div>

<script>
// DATA
let cart=JSON.parse(localStorage.getItem("oceanzx-cart"))||[];
let items=[
{name:"Crystal Egg",price:1,img:"https://image2url.com/r2/default/images/1769340250503-3d3f2972-9914-4529-9abd-abaf9b370d22.png",stock:3,rarity:"rare"},
{name:"Snow Owl NO POT",price:1.25,img:"https://image2url.com/r2/default/images/1769340321220-95e1be82-28fa-403a-a021-941d493283b8.png",stock:2,rarity:"epic"},
{name:"Reindeer Fly Ride",price:2.3,img:"https://image2url.com/r2/default/images/1769340396217-88705f92-43c7-4f07-97ca-2b5d1279ace3.png",stock:2,rarity:"legendary"},
{name:"Axolotl Fly Ride",price:2,img:"https://image2url.com/r2/default/images/1769312696977-97a3b12d-0869-4661-86d5-65f8f181744a.png",stock:3,rarity:"rare"},
{name:"Cerberus Fly Ride",price:3,img:"https://image2url.com/r2/default/images/1769312266778-b30a7b97-61bb-4650-bc6c-45a73512c0ba.jpg",stock:2,rarity:"epic"},
{name:"Dango Penguins",price:10,img:"https://image2url.com/r2/default/images/1769312623274-1c54447a-0b15-4ac9-a9b6-c875cecd6076.png",stock:1,rarity:"legendary"},
{name:"Neon Sneak Weasel (5)",price:12,img:"https://image2url.com/r2/default/images/1769312555909-e343e380-5694-43a1-9ddf-df2b262990c4.png",stock:2,rarity:"epic"},
{name:"Ride Sakura Spirit",price:8,img:"https://image2url.com/r2/default/images/1769312389581-e6410de1-5faa-4d25-8b23-dcf7c38fb51e.jpg",stock:1,rarity:"legendary"},
{name:"Snow Owl Fly Ride",price:2.5,img:"https://image2url.com/r2/default/images/1769312167327-6f2f8ab6-16e0-45d1-9730-dc8a16d6acdd.jpg",stock:4,rarity:"rare"}
];

// RENDER ITEMS
function renderItems(){
  const eggsGrid=document.getElementById("eggs-grid");
  const petsGrid=document.getElementById("pets-grid");
  eggsGrid.innerHTML=""; petsGrid.innerHTML="";
  items.forEach(it=>{
    const card=document.createElement("div");
    card.className="card "+it.rarity;
    card.innerHTML=`
      <img src="${it.img}">
      <h3>${it.name}</h3>
      <div class="price">$${it.price}</div>
      <div class="stock" data-stock="${it.name}">Stock: ${it.stock}</div>
      <button class="btn" data-btn="${it.name}" onclick="addToCart('${it.name}',${it.price})">Add to Cart</button>
    `;
    if(it.name.toLowerCase().includes("egg")) eggsGrid.appendChild(card);
    else petsGrid.appendChild(card);
  });
}

// CART FUNCTIONS
function updateCartCount(){
  document.getElementById("cart-count").innerText=cart.length;
}
function renderCart(){
  const itemsEl=document.getElementById("cart-items");
  let total=0; itemsEl.innerHTML="";
  cart.forEach((i,idx)=>{
    total+=i.price;
    itemsEl.innerHTML+=`<div class="cart-item"><span onclick="removeFromCart(${idx})">❌</span><span>${i.name}</span><span>$${i.price}</span></div>`;
  });
  document.getElementById("total").innerText=total.toFixed(2);
  updateCartCount();
  localStorage.setItem("oceanzx-cart",JSON.stringify(cart));
}
function addToCart(name,price){
  const it=items.find(i=>i.name===name);
  if(!it||it.stock<=0)return;
  cart.push({name,price}); it.stock--;
  renderCart(); updateStock(name);
}
function removeFromCart(idx){
  const r=cart.splice(idx,1)[0];
  const it=items.find(i=>i.name===r.name);
  if(it) it.stock++;
  renderCart(); updateStock(r.name);
}
function updateStock(name){
  const it=items.find(i=>i.name===name);
  const s=document.querySelector(`[data-stock="${name}"]`);
  const b=document.querySelector(`[data-btn="${name}"]`);
  if(it.stock<=0){s.innerText="❌ SOLD OUT"; b.disabled=true; b.innerText="Sold Out";}
  else{s.innerText=`Stock: ${it.stock}`; b.disabled=false; b.innerText="Add to Cart";}
}
function checkout(){
  if(cart.length===0) return alert("Cart empty");
  const id=Math.floor(Math.random()*900000+100000);
  let text=`🛒 Order (ID:${id})\n`; let total=0;
  cart.forEach(i=>{text+=`• ${i.name} - $${i.price}\n`; total+=i.price});
  text+=`\n💰 Total: $${total.toFixed(2)}`;
  navigator.clipboard.writeText(text);
  window.open("https://discord.com/users/1455058787257024512","_blank");
  cart=[]; renderCart(); localStorage.removeItem("oceanzx-cart");
}

// CART PANEL TOGGLE
document.getElementById("cart-btn").addEventListener("click",()=>{
  document.getElementById("cart-panel").classList.toggle("open");
});

// INIT
renderItems(); items.forEach(it=>updateStock(it.name)); renderCart();
</script>

</body>
</html>
