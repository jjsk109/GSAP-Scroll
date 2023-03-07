# GSAP-Scroll

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
