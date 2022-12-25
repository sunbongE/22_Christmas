# 2022_크리스마스

크리스마스는 역시... css와 함께

![Christmas_practice](Readme.assets/Christmas_practice-16719534419232.gif)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="/style.css">
    <script src="./index.js"></script>
    <title>Document</title>
</head>

<body>
    <div class="container">
        <div class="circle"></div>
        <div class="snow">
            <span style="--i:11;"></span>
            <span style="--i:12;"></span>
            <span style="--i:14;"></span>
            <span style="--i:17;"></span>
            <span style="--i:15;"></span>
            <span style="--i:26;"></span>
            <span style="--i:11;"></span>
            <span style="--i:21;"></span>
            <span style="--i:19;"></span>
            <span style="--i:13;"></span>
            <span style="--i:28;"></span>
            <span style="--i:11;"></span>
            <span style="--i:12;"></span>
            <span style="--i:14;"></span>
            <span style="--i:17;"></span>
            <span style="--i:15;"></span>
            <span style="--i:26;"></span>
            <span style="--i:11;"></span>
            <span style="--i:21;"></span>
            <span style="--i:19;"></span>
            <span style="--i:17;"></span>
            <span style="--i:15;"></span>
            <span style="--i:26;"></span>
            <span style="--i:11;"></span>
            <span style="--i:21;"></span>
            <span style="--i:19;"></span>
            <span style="--i:13;"></span>
            <span style="--i:28;"></span>
            <span style="--i:11;"></span>
            <span style="--i:12;"></span>
            <span style="--i:14;"></span>
            <span style="--i:17;"></span>
            <span style="--i:15;"></span>
            <span style="--i:26;"></span>
            <span style="--i:11;"></span>
            <span style="--i:21;"></span>
            <span style="--i:19;"></span>
            <span style="--i:13;"></span>
            <span style="--i:28;"></span>
        </div>

    </div>
</body>

</html>
```

only css

```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    background: linear-gradient(#a2000a, #cf0000);
}

.container {
    position: relative;
    width: 100%;
    height: 100vh;
    overflow: hidden;

}

.container::before {
    content: '';
    position: absolute;
    bottom: 0;
    width: 100%;
    height: 200px;
    background: url(./images/tree.png);
    z-index: 1;
}

.container .circle {
    position: absolute;
    top: 10%;
    left: 50%;
    /* 가운데로 보내려 했지만 요소에 왼쪽을 잡고 가운데로 보내주기 때문에*/
    transform: translateX(-50%);
    /* 요소의 절반만큼 왼쪽으로 보내줘야 딱 중앙에 잡힌다.*/
    width: 350px;
    height: 350px;
    background: #fff;
    border-radius: 50%;
}

.container .circle::before {
    content: '';
    position: absolute;
    inset: -200px -300px;
    background: url(./images/santa.png);
    background-position: center;
    background-repeat: no-repeat;
    background-size: 600px;
    animation: animate 5s ease-in-out infinite;
}

@keyframes animate {

    0%,
    100% {
        transform: translateY(-25px);
    }

    50% {
        transform: translateY(25px);
    }
}

.container .circle::after {
    content: 'Happy Christmas';
    position: absolute;
    inset: -125px -200px;
    font-size: 4em;
    display: flex;
    justify-content: center;
    align-items: flex-end;
    color: #fff;
}

.container .snow {
    position: relative;
    display: flex;
}

.container .snow span {
    position: relative;
    min-width: 5px;
    height: 5px;
    background: #fff;
    border-radius: 50%;
    margin: 0 1vw;
    box-shadow: -100px 20px 5px #fff,
        100px 20px 10px #fff;
    animation: animateSnow 15s linear infinite;
    animation-duration: calc(75s/ var(--i));
}

.container .snow span:nth-child(even) {
    min-width: 10px;
    height: 10px;
}

@keyframes animateSnow {
    0% {
        transform: translateY(-10vh);
    }

    100% {
        transform: translateY(100vh);
    }
}
```

