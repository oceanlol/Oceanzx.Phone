<!DOCTYPE html>
<html>

<head>

<title>
BLUE HORIZON STUDIOS | GET THE COUPONS
</title>


<meta name="viewport" content="width=device-width, initial-scale=1.0">


<style>

@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;500;700;900&display=swap');


*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:Poppins,sans-serif;
}


body{

background:#020617;

overflow:hidden;

color:white;

}



/* GLOBAL SCREEN */

.screen{

height:100vh;

width:100%;

display:flex;

align-items:center;

justify-content:center;

flex-direction:column;

}




/* BACKGROUND EFFECT */


.stars{

position:absolute;

width:100%;

height:100%;


background-image:

radial-gradient(
white 1px,
transparent 1px
);


background-size:70px 70px;

opacity:.25;


animation:stars 25s linear infinite;

}



@keyframes stars{

from{

transform:translateY(0);

}

to{

transform:translateY(200px);

}

}





/* STUDIO INTRO */


.studio{

background:black;

z-index:5;

}



.studio h1{

font-size:75px;

letter-spacing:12px;

font-weight:900;

text-align:center;

animation:fade 3s;

}



.studio h2{

margin-top:30px;

font-size:35px;

letter-spacing:18px;

color:#ccc;

animation:fade 5s;

}




@keyframes fade{

from{

opacity:0;

transform:scale(.8);

}

to{

opacity:1;

transform:scale(1);

}

}




/* MAIN MENU */


.menu{

position:relative;

background:

radial-gradient(
circle at top,
#006eff,
#020617 70%
);

}



.logo{

font-size:22px;

letter-spacing:8px;

color:#63ddff;

font-weight:700;

}



.tagline{

margin-top:10px;

font-style:italic;

color:#aaa;

}




.title{

font-size:80px;

margin-top:40px;

font-weight:900;


background:

linear-gradient(
90deg,
white,
#00eaff,
#4169ff
);


-webkit-background-clip:text;

color:transparent;

}



.subtitle{

font-size:25px;

color:#ddd;

}



.button{


margin-top:60px;

padding:22px 90px;

border-radius:60px;

border:none;

cursor:pointer;


font-size:28px;

font-weight:900;


color:white;


background:

linear-gradient(
90deg,
#006eff,
#00eaff
);


box-shadow:

0 0 60px #00eaff;


transition:.3s;


}



.button:hover{

transform:scale(1.1);

}




</style>

</head>


<body>


<div id="app"></div>



<script>


const app=document.getElementById("app");



function studioIntro(){


app.innerHTML=`

<div class="screen studio">

<h1>
BLUE HORIZON STUDIOS
</h1>

<h2>
PRESENTS
</h2>

</div>

`;



setTimeout(mainMenu,6000);


}



function mainMenu(){


app.innerHTML=`

<div class="stars"></div>


<div class="screen menu">


<div class="logo">

BLUE HORIZON STUDIOS

</div>


<div class="tagline">

"Beyond the edge of imagination."

</div>


<div class="title">

🎟️ GET THE COUPONS

</div>


<div class="subtitle">

A Collection Adventure

</div>



<button class="button" onclick="worldOne()">

▶ START GAME

</button>


</div>

`;

}



function worldOne(){


app.innerHTML=`

<div class="screen menu">


<h1>

🏡 HOME HORIZON

</h1>


<p>

Your first adventure begins.

Discover hidden coupons around your world.

</p>



<button class="button" onclick="couponSelect()">

🎟️ CHOOSE COUPONS

</button>


</div>

`;

}



function couponSelect(){


alert("Coupon Selection Loading...");


}



studioIntro();


</script>


</body>

</html>
