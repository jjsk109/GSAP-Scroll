﻿# GSAP-Scroll

### 스크롤 이벤트 
<h3> 목표 </h3>
<div>
    <dl>1. 스크롤을 내리다가 중간에 화면이 고정이 되야 한다.</dl>
    <dl>2. 스크롤을 내리며 이벤트 동작을 해야 한다.</dl>
    <dl>3. 이벤트가 다 동작하면 스크롤이 계속 내려가야 한다.</dl>
    <br/>
    <dl>이벤트1 : 동작 폭이 늘어나야 한다</dl>
    <dl>이벤트2 : 숫자를 변경을 해야한다</dl>
</div>
<br/>
<br/>
<br/>
<h3> 사용 툴 </h3>
<div>
    <dl>
        Green Sock (gsap) ScrollTrigger
    </dl>
    
</div>
<h3> 히스트리 </h3>
<div>
    <dl>
        1. EventTarget.addEventListener()
        <p>
            직접 하나하나 구현해야 하는 어려움이 있음 
            <br/>
            : 스크롤 위치 계산 
        </p>
    </dl>
    <dl>
        2. IntersectionObserver()
        <p>
            화면 멈추는 기능을 못함
            <br/>
            : 못찾은
        </p>
    </dl>
</div>

  <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            width: 100%;

        }

        div {
            margin: 0 auto;
            width: 600px;
            height: 1000px;
            position: relative;
            text-align: center;

        }

        #container1 {
            width: 100%;
            height: 1000px;
            position: relative;
            margin: 0 auto;
            overflow: hidden;
            background-image: linear-gradient( rgba(0, 0, 0, 0.6), rgba(0, 0, 0, 0.3) ),url(./KakaoTalk_20230220_075620887.jpg);
            background-size: cover;
            
        }

        #container2 {
            width: 600px;
            height: 1000px;
            position: relative;
            margin: 0 auto;
            overflow: hidden;
        }

        .box {
            width: 100%;
            height: 1000px;
            position: absolute;
        }
        .boxC{
            position: relative;
            top: 40%;
            left: 0%;
            width: 500px;
            height: 200px;
            transform: translate(-0%, -0%);
            border: 5px solid #fff;
            border-radius: 5px;
            overflow: hidden;
            background-color: rgba(0, 0, 0, 0.5);
        }
        .box1 {
            top: 0%;
            left: 0;
            transform: translate(0%, 0%);
        }

        .box2 {
            height: 400px;
            bottom: 0%;
            left: 0%;
            transform: translate(0%, 0%);
            font-size: 32px;
            font-weight: bold;
            color: #fff;
        }

        .box3 {
            top: 0%;
            left: 0%;
            margin: 0;
            width: 0px;
            height: 200px;
            transform: translate(-0%, -0%);
            background-color: rgb(51, 255, 0);
        }

        .box4 {
            height: 400px;
            bottom: 0%;
            left: 0%;
            transform: translate(0%, 0%);
        }
    </style>
</head>

<body>
    <div>첫 번째 문장</div>
    <div>두 번째 문장</div>
    <div>세 번째 문장</div>
    <div id="doc">네 번째 문장</div>
    <div id="container1">
        <div class="box box1">다섯 번째 문장</div>
        <div class="box box2"><span>0</span>%</div>
        <div  class="boxC">
            <div class="box box3"></div>
        </div>
    </div>
    <div>아홉 번째 문장</div>
    <div>열 번째 문장</div>
 
    <script>
        gsap.registerPlugin(ScrollTrigger);
        gsap.defaults({ ease: "none", duration: 2 });

        // 타임라인 설정
        const tl1 = gsap.timeline();

        // box 위치에 따른 이벤트 설정
        tl1.from(".box1", { scrollTrigger: ".box1", xPercent: -100 })
            .to(".box2 span", {  textContent: Math.ceil('100'), duration: 2 })
            .to(".box3", {width: "500px" })

        // 스크롤 이벤트 진행
        ScrollTrigger.create({
            animation: tl1,
            trigger: "#container1",
            start: "top top",
            end: "+=4000",
            scrub: true,
            pin: true,
            anticipatePin: 1
        })

    </script>
</body>
