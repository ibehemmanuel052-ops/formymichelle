# formymichelle
A code I made for you specially 
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For Michelle ❤️</title>

<link href="https://fonts.googleapis.com/css2?family=Pacifico&family=Dancing+Script:wght@600&family=Poppins:wght@300;500&display=swap" rel="stylesheet">

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

body{
    height:100vh;
    overflow:hidden;
    display:flex;
    justify-content:center;
    align-items:center;
    text-align:center;
    color:white;
    font-family:'Poppins', sans-serif;
    background: linear-gradient(to top, #ff4da6, #ff99cc);
    animation:sunrise 10s ease-in-out infinite alternate;
}

/* Sunrise animation */
@keyframes sunrise{
    0%{background:linear-gradient(to top, #ff4da6, #ff99cc);}
    100%{background:linear-gradient(to top, #ff9966, #ff5e62);}
}

.page{
    display:none;
    padding:20px;
    animation:fadeIn 1s ease-in-out;
}

.active{
    display:block;
}

h1{
    font-family:'Pacifico', cursive;
    font-size:2rem;
    margin-bottom:20px;
}

.name{
    font-family:'Dancing Script', cursive;
    font-size:2.3rem;
    margin-bottom:20px;
}

button{
    padding:12px 25px;
    margin:10px;
    border:none;
    border-radius:30px;
    font-size:1.2rem;
    cursor:pointer;
    transition:0.3s;
}

#yes{
    background:white;
    color:#ff1493;
}

#no{
    background:#ff4d6d;
    color:white;
}

@keyframes fadeIn{
    from{opacity:0; transform:scale(0.9);}
    to{opacity:1; transform:scale(1);}
}

/* Floating hearts */
.heart{
    position:absolute;
    animation:float 6s linear infinite;
}

@keyframes float{
    0%{transform:translateY(100vh); opacity:1;}
    100%{transform:translateY(-10vh); opacity:0;}
}
</style>
</head>

<body>

<!-- Background Music -->
<audio autoplay loop>
    <source src="music.mp3" type="audio/mpeg">
</audio>

<!-- PAGE 1 -->
<div class="page active" id="page1">
    <div class="name">Michelle ❤️ <br> My Sugar Plum ❤️</div>
    <h1>Would you love to spend every sunrise and sunset with me? 🌅❤️</h1>
    <button id="yes" onclick="goToPage2()">Yes 💕</button>
    <button id="no" onclick="shrinkNo()">No 😢</button>
</div>

<!-- PAGE 2 -->
<div class="page" id="page2">
    <h1>Thank you for making me the happiest man on earth ❤️🥹</h1>
    <button onclick="goToPage3()">Continue 💌</button>
</div>

<!-- PAGE 3 -->
<div class="page" id="page3">
    <h1>Happy Valentine’s Day My Love 💖</h1>
    <p style="max-width:600px; margin:auto; font-size:1.1rem;">
        Even though we’re miles apart, every day I wake up with a smile 
        because I know that you’re in my life.  
        Each sunrise reminds me of your warmth, 
        and each sunset brings me closer to seeing you again.  
        I may not be there in person, but I’m holding you in my heart, always.  
        You are deeply loved, endlessly cherished, and forever mine. ❤️
    </p>
</div>

<script>
let noSize = 1;
let yesSize = 1;

function shrinkNo(){
    noSize -= 0.1;
    yesSize += 0.1;

    document.getElementById("no").style.transform = `scale(${noSize})`;
    document.getElementById("yes").style.transform = `scale(${yesSize})`;

    if(noSize <= 0.3){
        document.getElementById("no").style.display="none";
    }
}

function goToPage2(){
    document.getElementById("page1").classList.remove("active");
    document.getElementById("page2").classList.add("active");
}

function goToPage3(){
    document.getElementById("page2").classList.remove("active");
    document.getElementById("page3").classList.add("active");
}

/* Floating hearts generator */
function createHeart(){
    const heart = document.createElement("div");
    heart.classList.add("heart");
    heart.innerHTML = "❤️";
    heart.style.left = Math.random()*100 + "vw";
    heart.style.fontSize = Math.random()*20 + 15 + "px";
    document.body.appendChild(heart);

    setTimeout(()=>{heart.remove();},6000);
}

setInterval(createHeart,500);
</script>

</body>
</html>