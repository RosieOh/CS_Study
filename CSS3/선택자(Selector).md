# 1. 선택자의 종류

## 🥭 계층 선택자

- 조상-후손 선택자 : `조상 후손 {  }`
- 부모-자식 선택자 : `부모 > 자식 {  }`
- 형-제 선택자 : `형 ~ 제 {  }`
- 순서 선택자 : `형 + 바로밑의동생 {  }`

```html
<div class="ex1">
    <nav class="gnb">
        <ul class="lst1">
            <li class="item1"><a href=""> 항목1 </a></li>
            <li class="item2"><a href=""> 항목2 </a></li>
            <li class="item3"><a href=""> 항목3 </a></li>
        </ul>
        <ol class="lst2">
            <li class="item1"><a href=""> 항목1 </a></li>
            <li class="item2"><a href=""> 항목2 </a></li>
            <li class="item3"><a href=""> 항목3 </a></li>
        </ul>
    </nav>
</div>

<style>
		.ex1 li {  }<br>                        <!-- ex1 클래스의 후손 중에서 li 요소를 선택 -->
    .ex1 > nav > .lst1 > li {  }<br>        <!-- ex1 클래스부터 그 안의 모든 노드를 모두 기재 -->
    .ex1 .item1 ~ li {  }<br>               <!-- item1 클래스의 동생들을 선택 -->
    .ex1 .item1 + li {  }<br>               <!-- item1 클래스의 바로 다음의 li 하나만 선택-->
    li:first-child {  }<br>                 <!-- 첫 번째 자식 선택 -->
    li:first-of-type a {  }<br>             <!-- 첫 번째 요소 선택 -->
    li:last-child {  }<br>                  <!-- 마지막 자식 선택 -->
    li:last-of-type {  }<br>                <!-- 마지막 요소 선택 -->
    li:nth-child(2) {  }<br>                <!-- 두 번째 자식 선택 -->
    li:nth-of-type(2) {  }<br>              <!-- 두 번째 요소 선택 -->
    li:nth-child(2n+1) {  }<br>             <!-- 홀수 번째 자식 선택 -->
    li:nth-child(2n) {  }<br>               <!-- 짝수 번째 자식 선택 -->
    li:only-child {  }<br>                  <!-- 해당 요소가 하나만 있는 자식 선택 -->
    li:only-of-type {  }<br>                <!-- 해당 요소가 하나만 있는 요소 선택 -->
    li:empty::after {  }<br>                <!-- 자식이 없거나 내용이 비어 있는 요소 선택 -->
</style>
```

## 🥭 속성 선택자

- 태그의 속성에 따라 다르게 선택할 경우 사용

| 이미지 중에서 src 속성이 존재하는 경우 | img[src] {  } |
| --- | --- |
| 이미지 중에서 src 속성의 값이 정확하게 일치하는 요소 선택 | img[src=”mbc.jpg”] {  } |
| 이미지 중에서 src 속성의 값이 특정 문자로 시작하는 요소 선택 | img[src|=”문자”] {  }
img[src^=”문자”] {  } |
| 이미지 중에서 src 속성의 값이 특정 문자로 끝나는 요소 선택 | img[src$=”문자”] {  } |
| 이미지 중에서 src 속성의 값이 특정 문자가 포함되는 요소 선택 | img[src*=”문자”] {  }
img[src~=”문자”] {  } |

## 🥭 링크 선택자

- 하이퍼링크 요소인 a요소의 현재 동작상태에 따라 달리 적용됨
    - a 요소에 href 속성의 값이 있는 경우 : `link`
    - a 요소에 href로 지정된 url에 방문한 적이 있는 경우 : `visited`
    - 요소에 마우스 포인터가 올라가는 경우 : `hover`
    - 요소에 마우스를 누르고 있는 경우 : `active`
    
    ```css
    /* 꼭 아래의 순서를 지켜야 함 */
    a:link {  }
    a:visitied {  }
    a:hover {  }
    a:active {  }
    ```
    

## 🥭 전후 선택자

```css
a:before { content: "앞" }
a:after { content: "뒤" }
```

- 지정한 요소의 내용 앞뒤에 스타일을 넣을 수 있음
- 이 요소를 사용하면 요소의 앞뒤에 텍스트나 이미지 등을 추가할 수 있음
- `:after` VS `::after`
    - `:after`은 CSS2에서, `::after`은 CSS3에서 사용

## 🥭 텍스트 / 문장 선택자

```css
/* 첫 글자 선택자 */
.className::first-letter {  }
/* 첫줄 선택자 */
.className::first-line {  }
```

- `::first-line`은 창을 줄여서 첫 번째 줄의 글자가 두 번째 줄로 내려갔어도 첫 번째 줄에만 스타일이 적용됨

## 🥭 타겟 선택자

```css
#app1, #app2, #app3 { width: 500px; height: 300px; text-align: center; font-size: 40px; line-height: 300px; border: 3px solid #333; height: 0px; 
                overflow: hidden; box-sizing: border-box; transform: 0.6s; }
        
#app1:target, #app2:target, #app3:target { height: 300px; }
```

- 문서에서 같은 사이트나 다른 사이트의 페이지로 이동할 때에는 링크를 이용하고, 같은 문서 안에서 다른 위치로 이동할 때에는 앵커 이용
- `:target` 선택자를 사용하면 앵커로 연결된 부분, 즉 앵커의 목적지가 되는 부분의 스타일을 쉽게 적용할 수 있음

## 🥭 부정 선택자 / 체크 선택자 / 포커스 선택자

- 부정 선택자 - `not(:가상선택자)`
- 체크 선택자 - `:checked`
- 포커스 선택자 - `:focus`

```html
<div class="tab_box">
    <label for="ra1"> 선택1 </label>
    <label for="ra2"> 선택2 </label>
    <label for="ra3"> 선택3 </label>
    <input type="radio" name="ra" id="ra1" class="ra" checked>
    <div class="tab" id="tab1"> 탭박스1 </div>
    <input type="radio" name="ra" id="ra2" class="ra">
    <div class="tab" id="tab2"> 탭박스2 </div>
    <input type="radio" name="ra" id="ra3" class="ra">
    <div class="tab" id="tab3"> 탭박스3 </div>
</div>
```

```css
.tab { width:800px; line-height: 300px; text-align: center; font-style: 38px; overflow: hidden; transition: 0.7s; }
.ra { display: none; }
.ra:not(:checked) + .tab { height:0px; }
.ra:checked + .tab { height: 300px; }
```

# 2. 선택자 우선순위

- 선택자 우선순위란 같은 요소가 여러 선언의 대상이 된 경우, **어떤 선언의 CSS 속성을 우선적으로 적용할 것인지**를 결정하는 방법
    1. 점수가 높은 선언이 우선함
    2. 점수가 같으면, 가장 마지막에 작성된 선언이 우선함

## 🍓 선택자 점수 매기기

### 🥇 아이디

### 🥈 클래스

### 🥉 태그