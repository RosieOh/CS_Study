# CSS 속성(Properties)

## CSS 출력 및 박스 관련 속성

- display, visibility, opacity, width, height, overflow, margin, padding, border 등
- 모든 속성의 값에 initial(초기값), inherit(부모 요소로 부터 상속)

---

## display : 화면 출력 모드를 지정하는 속성

- 태그마다 화면 출력 모드가 block, inline, inline-block 등으로 구성됨.
- inline 속성 요소 : span, a, strong, em, ins 등
- inline 요소의 특징 : 한 줄 안에 자동 줄바꿈이 될 때까지 배치되며, 크기 지정을 할 수 없어 width, height, line-height, text-indent, text-align, padding-top, padding-bottom, margin-top, margin-bottom 등 속성을 지정한다고 하더라도 결과에 반영되지 못한다.
- block 속성 요소 : div, h1 ~ h6, p, section, article, header, footer,... 등이 있음
- 자동으로 다음 줄에 배치가 되며, 크기와 관련된 속성을 지정할 수 있음
- 부여 가능한 속성의 값 : inline | block | inline-block | none
- 부여 가능한 속성의 값2 : contents. flex, grid, box, table, inline-flex, inline-grid, inline-table, list-item, run-in, table-caption, table-column, table-row, table-cell, table-header-group, table-footer-group, table-column-group, table-row-group 등

---

## visibility(가시 속성)

- 보일지 보이지 않을 지를 나타내는 속성
- visible | hidden | collapse

---

## opacity(불투명도 속성)

- 불투명 정도를 나타내는 속성
- 0~1 까지의 실수 또는 정수로 표시하며, 0은 투명, 1은 불투명
- 해당 요소의 글자와 배경색/배경이미지를 포함한 모든 콘텐츠를 불투명 또는 투명하게 지정할 수 있음

---

## width(너비 속성)

가로(폭=너비)의 크기를 지정하는 속성

auto | length | %

length는 px, pt, pc, cm, mm, in, vw, vmin, vmax 등의 단위로 지정이 가능

기본 화면 출력 속성이 블록요소 또는 인라인블록요소 등에만 크기 지정이 가능함.

---

## height(높이속성)

세로(높이)의 크기를 지정하는 속성

auto | length | %

length는 px, pt, pc, cm, mm, in, vw, vmin, vmax 등의 단위로 지정이 가능

기본 화면 출력 속성이 블록요소 또는 인라인 블록요소 등에만 크기 지정이 가능함.

---

## overflow(흘러넘침속성)

콘텐츠의 양이 지정한 크기(폭/높이)보다 더 클 경우 지정

visible | hidden | scroll | auto | clip

### 세부 속성 : overflow-x(가로), overflow-y(세로)

---

## margin(바깥여백)

현재 테두리(콘텐츠) 영역의 바깥 여백으로서 여러 콘텐츠와 콘텐츠 사이의 여백

auto | length | %

length는 px, pt, pc, cm, mm, in, vw, vmin, vmax 등의 단위로 지정이 가능

margin:값, margin:위/아래 좌/우, margin:상 우 하 좌

### 세부 속성 : margin-top, margin-bottom, margin-left, margin-right

※ 통합 속성을 먼저 지정하고, 세부 속성을 나중에 지정하여야 세부 속성이 적용됨

---

## padding(안쪽여백)

테두리와 콘텐츠 사이의 여백

auto | length | %

length는 px, pt, pc, cm, mm, in, vw, vmin, vmax 등의 단위로 지정이 가능

padding: 값, padding: 위/아래/ 좌/우, padding:상 우 하 좌

### 세부 속성 : padding-top, padding-bottom, padding-left, padding-right

※ 통합 속성을 먼저 지정하고, 세부 속성을 나중에 지정하여야 세부 속성이 적용되며, 지정한 폭/높이에 padding과 border 값을 더한 값이 실제 배치(적용) 크기가 된다.

### border(테두리)

border : width style color

ex) border : 1px solid #000;

1px 두께의 검은색 실선

width는 선의 두께로서 px, pt, pc, cm, mm, in, vw, vmin, vmax 등의 단위로 지정이 가능

style은 선의 모양으로서 solid, none, hidden, dotted, dashed, double, groove, ridge, inset, outset 등의 지정이 가능

color는 선의 색으로서 컬러명, 16진(hex)코드, rgb()/rgba(), hsl/hsla() 등으로 지정이 가능

### 카테고리별 세부 속성

### border-width(선두께)

ex1) border-width:2px

ex2) border-width:2px 5px

ex3) border-width:2px 5px 10px 20px

### border-style(선종류)

ex1) border-style:solid

ex2) border-style:solid dashed

ex3) border-style:solid dashed double hidden

### border-color(선색상)

ex1) border-color:red

ex2) border-color:red blue

ex3) border-style:blue gold navy orange

### 방향별 세부 속성

### border-left(왼쪽 테두리)

ex1) border-left : 2px double silver

### border-right(오른쪽 테두리)

ex2) border-right : 5px dotted gold

### border-top(위쪽 테두리)

ex3) border-top : 3px dashed deepskyblue

### border-bottom(아래쪽 테두리)

ex4) border-bottom : 4px ridge deeppink

### 세세 속성

border-left-width, border-left-style, border-left-color

border-right-width, border-right-style, border-right-color

border-top-width, border-top-style, border-top-color

border-bottom-width, border-bottom-style, border-botton-color

각 방향별로 선 두께, 선 종류, 선 색상을 개별적으로 지정할 수 있음

## box-sizing(박스의 크기 산정방법)

박스의 크기를 지정한 너비/높이가 콘텐츠까지만 적용할지, padding과 border를 포함하여 적용할지 등의 여부를 지정

content-box | border-box

content-box는 지정한 너비/높이가 콘텐츠에만 적용, border-box는 지정한 너비/높이에 콘텐츠+padding+border로 적용됨

---

## border-radius(테두리둥글기)

값으로는 px, pt, pc, cm, mm, in, vw, vmin, vmax 등의 단위로 지정이 가능

ex1) border-radius:20px;

ex2) border-radius:50%;

ex3) border-radius:20px 50px;

ex4) border-radius:10px 20px 30px 40px;

ex5) border-top-left-radius:20px;

ex5) border-top-right-radius:20px;

ex5) border-bottom-right-radius:20px;

ex5) border-bottom-left-radius:20px;