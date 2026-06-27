<html lang="de">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Eine wichtige Frage ❤️</title>

<style>
body{
    margin:0;
    height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    background:linear-gradient(135deg,#ff9ec4,#ffd6e7);
    font-family:Arial,sans-serif;
    overflow:hidden;
}

.box{
    text-align:center;
    background:white;
    padding:40px;
    border-radius:20px;
    box-shadow:0 10px 30px rgba(0,0,0,.2);
}

h1{
    margin-bottom:35px;
}

button{
    font-size:22px;
    padding:15px 35px;
    margin:10px;
    border:none;
    border-radius:12px;
    cursor:pointer;
    transition:.2s;
}

#yes{
    background:#4CAF50;
    color:white;
}

#no{
    background:#e53935;
    color:white;
    position:absolute;
}
</style>

</head>
<body>

<div class="box">
    <h1>Willst du mit mir gv? 😊</h1>

    <button id="yes">Ja ❤️</button>
</div>

<button id="no">Nein, ich hab Bauchi 😢</button>

<script>

const no = document.getElementById("no");
const yes = document.getElementById("yes");

function moveButton(){

    const maxX = window.innerWidth - no.offsetWidth;
    const maxY = window.innerHeight - no.offsetHeight;

    no.style.left = Math.random()*maxX + "px";
    no.style.top = Math.random()*maxY + "px";
}

// Startposition
moveButton();

// Maus kommt in die Nähe
document.addEventListener("mousemove",(e)=>{

    const rect = no.getBoundingClientRect();

    const dx = e.clientX - (rect.left + rect.width/2);
    const dy = e.clientY - (rect.top + rect.height/2);

    const distance = Math.sqrt(dx*dx + dy*dy);

    if(distance < 120){
        moveButton();
    }

});

yes.onclick = ()=>{
    alert("Jaaaa! 🥳 LEEEETS GOOO ❤️");
}

</script>

</body>
</html>
