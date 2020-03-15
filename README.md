```
<ul>은 뭐고 <li>는 뭔지...

The HTML <li> element is used to represent an item in a list. It must be contained in a parent element: an ordered list (<ol>), an unordered list (<ul>), or a menu (<menu>). In menus and unordered lists, list items are usually displayed using bullet points. In ordered lists, they are usually displayed with an ascending counter on the left, such as a number or lette

https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li
```

창을 줄이면 ... 배치가 이상해지는 문제가 있습니다..

## nav영역

- html 뼈대 잡기

```html
    <nav>
      <img src="images/logo.png">
      <ul calss="nav-items">
        <li class="nav-item">Home</li>
        <li class="nav-item">Community</li>
        <li class="nav-item">Login</li>
      </ul>
    </nav>
```

- home, community, login 한줄 배치

  ```
  .nav-item {
    display: inline
  }
  ```

  - bullet point 세 줄 사라지고 한 줄로 바뀜
  - 왜 .nav-items가 아닌 .nav-item에 inline을 줘야 한 줄로 바뀔까? 

- 로고 이미지 넣어야함

  ```html
  <a href="04_community.html"><img src="images/logo.png" alt="로고이미지를 클릭하면 새로운 페이지로 이동합니다" height="80px"></a>
  ```

- 로고 사진과 .nav-items를 좌/우측으로 보내기

  ```
  .nav-items {
    float: right;
  }
  ```

  - 로고 사진은 그대로 두면 되는듭..?! 

- .nav-items가 같은 줄이 아니므로 마진 줘서 같은 줄로 만들기

  ```css
  .nav-items {
    float: right;
    margin: 0;
    padding: 0;
  }
  ```

- 항상 float clear를 하는 습관을 통해 예상치 못한 결과를 방지합니다.?? 0313review 리드미 무슨 뜻인지..그냥 복붙 했어요...ㅠ

  ```css
  .nav::after {
    content:'';
    display:block;
    clear:right;
  }
  ```

- nav-item 에 링크를 각각 연결해줌 

  ```html
   <nav>
       <img src="images/logo.png" alt="로고이미지를 클릭하면 새로운 페이지로 이동합니다">
       <a herf="04_community.html"></a>
       <ul class="nav-items">
          <li class="nav-item">
            <a href="03_home.html">Home</a>
          </li>
          <li class="nav-item">
            <a href="04.community.html">Community</a>
          </li>
          <li class="nav-item">
            <a href="04.community.html">Login</a>
          </li>
        </ul>
      </nav>   
  ```

- 링크가 연결된 것의 밑줄을 지워줌 & 글자 색 지정

  ```css
  .nav-item>a {
    text-decoration: none;
    color:  white;
  }
  ```

  - .nav-item 에서 텍스트 데코레이션을 해주는 것이 아니라 a까지 들어와서 하기
    - 왜 nav-item에서 해주면 안되고 a까지 들어와서 해줘야할까..

- nav 스타일링 

  ```css
  nav {
      padding: 2rem
      background-color: violet;
  }
  ```

  - rem이란?즉 html 요소의 크기의 몇 배인지로 크기를 정합니다. https://www.codingfactory.net/10748
  
- .nav-item 스타일링 추가; 수직정렬, 리스트의 각 항목간 간격 

  ```css
  .nav-item {
    display: inline;
    height: 80px;
    line-height: 80px;
    padding: 16px;
    
  }
  ```

   - height에 물결 밑줄이 뜹니다...! 왜..?

   - 창 크기를 줄이면 이상해짐.. 해결책은,.,?

     ![image-20200314225932801](C:\Users\namu\AppData\Roaming\Typora\typora-user-images\image-20200314225932801.png)

  ![image-20200314224203624](C:\Users\namu\AppData\Roaming\Typora\typora-user-images\image-20200314224203624.png)

- 네이게이션 리스트 마우스 올렸을 때, 글자색이 바뀌어야 함

  ```css
  a:hover {
    color: palegoldenrod;
  }
  ```

- 추가) 메뉴클릭 범위 키우는 법 

  - https://ironsky.tistory.com/21
  
- 네비게이션 바 상단 고정

  ```css
  nav {
      position: fixed;
      top: 0;
      left: 0;
      right: 0;
  }
  ```

  

## footer 영역

- html 뼈대 잡기

  ```html
  <!DOCTYPE html>
  <html lang="en">
    <head>
      <meta charset="UTF-8" />
      <meta name="viewport" content="width=device-width, initial-scale=1.0" />
      <title>PJT02</title>
      <!-- Default -->
      <link rel="stylesheet" href="style.css" />
      <!-- 02_footer.css -->
      <link rel="stylesheet" href="02_footer.css" />
    </head>
    <body>
      <!-- 02_footer.html -->
      <!-- 아래에 코드를 작성해 주세요. -->
      <footer> HTML&CSS project Created by PARK SeonYeong , 2020 </footer>
    </body>
  </html>
  ```

- footer 스타일링

  ```css
  footer {
      position:fixed; 
      left: 0;
      right: 0;
      bottom: 0;
      height: 60px;
      line-height: 60px;
      text-align: center;
      background: silver;
      color: white;
  }
  ```

  ![image-20200315124358878](C:\Users\namu\AppData\Roaming\Typora\typora-user-images\image-20200315124358878.png)

  [https://webcoding.tistory.com/entry/CSS3-position-%EC%86%8D%EC%84%B1%EC%9D%84-%EC%82%AC%EC%9A%A9%ED%95%98%EC%97%AC-%EC%9A%94%EC%86%8C-%EB%B0%B0%EC%B9%98%ED%95%98%EA%B8%B0](https://webcoding.tistory.com/entry/CSS3-position-속성을-사용하여-요소-배치하기)

## home- header영역

- html 구조

  ```html
      <header class="cover" >
          <ul class='cover-items'>
            <h1 class="cover-title">cinema<br>community</h1>
            <button class="cover-button">Let's Go</button>
          </ul>
        
      </header>   
  ```

- 커버 배경 이미지 설정

  ```css
  .cover {
      background-image: url("images/header.jpg");
      background-repeat: no-repeat;
      background-size: auto;
      }
  ```

  - background-image 높이가 0, 세로 크기가 안잡혀서 사진이 이상한건가...
    - height: 500px; 으로 일단 줌 

- 커버 포지션 relative로 설정해서 네비게이션 바 높이 만큼 내려주기

  ```css
  .cover {
    
    background-image: url("images/header.jpg");
    background-repeat: no-repeat;
    background-size: auto;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 500px;
    position: relative;
    top: 80px;
    
    
  }
  
  ```

- cover-title 범위가 이상하다... ? 

  - ![image-20200315145802170](C:\Users\namu\AppData\Roaming\Typora\typora-user-images\image-20200315145802170.png)

- 버튼 스타일링1

  ```css
  .cover-button {
    border-radius: .3rem;
    background-color: blue;
    color: white;
  }
  ```

- 버튼 보더, 높이, 너비, 마진탑 지정

  ```css
    border: 0;
    height: 2rem;
    width: 5rem;.cover-button {
    border-radius: .3rem;
    background-color: rgba(68, 107, 214, 0.849);
    color: white;
    border: 0;
    height: 2rem;
    width: 5rem;
    margin-top: 50px;
  
  }
  ```

- 버튼에 마우스 올렸을 때 배경색이 어둡게

  ```css
  .cover-button:hover {
    background-color: blue;
  }
  ```

  - 색깔 지정하지 말고 어둡게 자동 지정하는 방법이 있나?

## home-section 영역

- 세부분으로 나눠주기  + used skill도 추후에 문들어줘야함..!  어뜨캐..?ㅎㅎ

  ```html
      <section>
        <div class="contents" >
          <h2 class="contents-title">Used skills</h2>
          <div class="skills">
            <img class="skill" src="images/web.png" >
  
            <img class="skill"  src="images/html5.png">
  
            <img class="skill"  src="images/css3.png">
          </div>
        </div>
      </section>
  
  ```

- 하단 Section 내부의 요소(글, 버튼)는 스크롤을 최하단으로 내렸을 때, 수직으로 정렬되어 있습니 다. (위, 아래 여백이 같습니다.) 

- 이미지 크기 지정

  ```css
  .skill {
    
    width: 200px;
    height: 200px;
    
  }
  ```

- 세로로 3개 배치되어있는거 가로로 3개 나열 

  ````css
  .skills {
      display: flex;
      text-align: center;
      justify-content: center;
  ````

  - justify-content: center; Align the flex items at the center of the container:
  -  text-align: center; 를 skills에 넣는 이유를 모르겠음! 왜 skill에 넣으면 작동을 안할까?

- 이미지 밑에 캡션 넣기

  ```html
      <section>
        <div class="contents" >
          <h2 class="contents-title">Used skills</h2>
          <div class="skills">
            <div><img class="skill" src="images/web.png" ><br>WEB</div>
  
            <div><img class="skill"  src="images/html5.png"><br>HTML5</div>
  
            <div><img class="skill"  src="images/css3.png"><br>CSS3</div>
          </div>
        </div>
      </section>
  ```

  - caption https://www.w3schools.com/css/tryit.asp?filename=trycss_float3

  - 캡션 키워드가 생각이 안나서 검색하기가 어려웠음

- contents 영역과 cover 배경이미지 아래로 겹치고, 안보이는 문제 해결하기

  ```
  .contents {
      position: relative;
      padding-top: 100px;
  }
  ```

  - padding-top 임의로 안주고 다른 방법으로 하는 방법은?

  ![image-20200315182306480](C:\Users\namu\AppData\Roaming\Typora\typora-user-images\image-20200315182306480.png)

  ![image-20200315205806194](C:\Users\namu\AppData\Roaming\Typora\typora-user-images\image-20200315205806194.png)

  ![image-20200315205838384](C:\Users\namu\AppData\Roaming\Typora\typora-user-images\image-20200315205838384.png)

  

  

- used skil 가운데 정렬하고 마진 있길래 0으로 줌

  ```css
  .contents-title {
    text-align: center;
    margin: 0;
  }
  ```

  

## community

- html 

  ```html
      <div class="main">
        <div>
          <h1>자유게시판</h1>
          <hr>
        </div> 
  ```

  

- 네비게이션 바와 푸터를 제외한 주 영역( div.main ) 의 가로폭은 720px 입니다. + 좌우 마진을 통해 수평으로 정렬 

  ```css
  .main {
      width: 720px;
      margin: 0 auto;
      
  }
  ```

  - [https://skout90.github.io/2017/07/24/CSS/%EC%9A%94%EC%86%8C%EB%B2%8C-%EC%A0%95%EB%A0%AC%EB%B0%A9%EB%B2%95/](https://skout90.github.io/2017/07/24/CSS/요소벌-정렬방법/)

  - 좌우 마진을 통해 수평 정렬 방법이 마진 0 auto ./..이게 맞는지..?

- 주 영역의 h1 요소 수평 정렬

  ```css
  h1 {
      text-align: center;
  }
  ```

  - .main>h1으로 해야하는 지 헷갈렸음. h1으로 바로 해주면 됨! 

- hr 너비, 두께, 색, 그림자 없애기

  ```css
  hr {
    width: 100px;
    background-color: yellow;
    height: 3px;
    border:0px;
  
  }
  ```

  - hr은 닫는 태그가 없어도 됨

- 게시글은 글 제목 , 영화 제목 , 사용자 id , 작성시간 으로 구성되어 있으며 해당 구성을 유지해야 합니다. 

- ```html
        <section>
          <!-- 테스트용 게시글 -->
          <article>
            <div>
              <!--글 제목 -->
              <h2 id="title">Lorem ipsum dolor sit amet consectetur adipisicing elit.</h2>
              <!-- 영화제목  -->
              <span id="movie-title">test movie</span>
            </div>
            <div>
              <!-- 사용자 id -->
              <span id="user-id">user1</span>
              <!-- 작성시간 -->
              <span id="date">2020-**-** 12:34</span>
            </div>
          </article>
        </section>
      </div>
  ```

- 테스트 게시글 추가는 자유롭게 할 수 있습니다. 

- 각 article 요소의 글 제목 과 영화 제목 은 좌측 정렬, 사용자 id 와 작성시간 은 우측 정렬합니 다.

  ```html
      <!-- 04_community.html -->
      <div class="main">
        <div>
          <h1>자유게시판</h1>
          <hr>
        </div> 
  
        <section>
          <!-- 테스트용 게시글 -->
          <article>
            <div>
              <!--글 제목 -->
              <h2 id="title">Lorem ipsum dolor sit amet consectetur adipisicing elit.</h2>
              <!-- 영화제목  -->
              <span id="movie-title">test movie</span>
            </div>
            <div class="idanddate">
              <!-- 사용자 id -->
              <span id="user-id">user1</span>
              <!-- 작성시간 -->
              <span id="date">2020-**-** 12:34</span>
            </div>
          </article>
        </section>
      </div>
  ```

  - 사용자 id 와 작성자 id를 클래스로 묶어준 후 float: right 설정

    ```css
    .idanddate {
        float: right
    }
    ```

- 각 article 요소의 하단에만 테두리를 설정, padding-bottom으로 간격 줌  

  ```
  article {
      border-bottom: 1px solid slategray;
      padding-bottom: 3em;
  }
  ```

- 탑 줘서 네비게이션 바 밑에 메인 오도록 하기 

  ```css
  .main {
      position: relative;
      top: 80px;
      
  }
  ```

- id 글자색 변경하기

  ```css
  #movie-title {
      color: silver
  }
  #date {
      color: slategray;
  }
  ```

  

