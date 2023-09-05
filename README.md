# Catch Me

This is a simple game where the user tries to catch a box that moves around the screen. The box moves in a random direction and the user must use the mouse to move their cursor and catch the box.

# Html File
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Catch Me</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div id="box">
        <p>Catch Me</p>
    </div>
    <script src="script.js"></script>
</body>
</html>
```
# Css File
```
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
#box {
    width: 7vw;
    height: 7vw;
    background-color: #b916f4;
    cursor: pointer;
    position: absolute;
    display: flex;
    justify-content: center;
    align-items: center;
}

#box p {
    font-size: 1.4vw;
    color: white;
}
```
# Javascript File
```
var box = document.getElementById('box');
var viewWidth = window.innerWidth;
var viewHeight = window.innerHeight;
box.addEventListener("mouseover", function() {
    var boxAttr = box.getBoundingClientRect();
    var pos = getNewPosition(boxAttr.width, boxAttr.height);
    box.style.top = pos.y + "px";
    box.style.left = pos.x + "px";
});
function getNewPosition(boxWidth, boxHeight) {
    var newX = Math.floor((Math.random() * viewWidth)  - boxWidth);
    var newY = Math.floor((Math.random() * viewHeight)  - boxHeight);
    if(newX < 0) {
        newX = 0;
    }
    if(newY < 0) {
        newY = 0;
    }
    return {x: newX, y: newY};
}
```
