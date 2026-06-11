<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>สุ่มชื่อ</title>
<style>
body{
    text-align:center;
    font-family:Arial;
}
#wheel{
    width:250px;
    height:250px;
    border:10px solid #333;
    border-radius:50%;
    margin:30px auto;
    display:flex;
    justify-content:center;
    align-items:center;
    font-size:24px;
    font-weight:bold;
    transition: transform 4s ease-out;
}
button{
    padding:10px 20px;
    font-size:18px;
}
</style>
</head>
<body>

<h2>สุ่มชื่อ</h2>

<div id="wheel">กดหมุน</div>

<button onclick="spin()">หมุน</button>

<h3 id="result"></h3>

<script>
const names = [
    "สมชาย",
    "สมหญิง",
    "นัท",
    "ฟ้า",
    "ต้น"
];

let angle = 0;

function spin(){

    const winner =
        Math.floor(Math.random()*names.length);

    angle += 3600 + Math.floor(Math.random()*360);

    const wheel =
        document.getElementById("wheel");

    wheel.style.transform =
        `rotate(${angle}deg)`;

    setTimeout(()=>{
        document.getElementById("result")
            .innerHTML =
            "ผลลัพธ์: " + names[winner];

        wheel.innerHTML = names[winner];
    },4000);
}
</script>

</body>
</html>
