# css(Cascading Style Sheet)
## css 작성 전 준비사항 
* html 문서 준비(태그 작성 완료 상태)
* html, css 파일 별도 폴더 관리 
* 최상위 폴더 html 파일 배치
* 하위 폴더명 css, styles 으로 css파일 배치 
* ex) index.html, index.css 
## css 외부스타일시트와 내부스타일시트
* name.css 외부파일로 분리해서 html에 link로 연결하는 **외부 스타일시트** 
* html파일 내에서 head태그 안에 style태그로 구분해서 작성하는 **내부 스타일시트**
* 외부스타일시트 장단점 :
- 장점 : 1개의 css 파일로 여러개의 html을 관리할 수 있다. 
- 단점 : 파일명 또는 파일 위치를 정확히 관리하지 않으면 파일 관리가 어려울 수 있다.  
* 내부스타일시트 장단점 :
- 장점 : html파일 내에 작성하여 태그와 한꺼번에 보기 편하다. 
- 단점 : 2개이상의 html파일을 동시에 디자인관리하는 것이 불가능하다. 
## css 선택자 
1. 태그선택자 : `<h1></h1>` -> `h1 {속성:값;}`
2. 클래스선택자 : `<h1 class="a"></h1>` -> `.a {속성:값;}`
3. 아이디선택자 : `<h1 id="b"></h1>` -> `#b {속성:값;}`
4. 자손선택자 : `<h1><em><span></span></em></h1>` -> `h1 em span {속성:값;}`
5. 자식선택자 : `<h1><em><em></em></em></h1>` -> `h1 > em {속성:값;}`
## css 디자인하기 
* css 작성 전 HTML이 미리 디자인이 되어있으면 안된다. 
* **HTML을 디자인 초기화하는 작업이 css 디자인 전 반드시 선행되어야 한다!!!**
* 초기화 css `reset.css` 공통파일 (날짜나 프로젝트명 표기금지!)
# css 글자 표현 속성 
## font-family
* 로컬글꼴(설치글꼴제공) 또는 웹 글꼴(추천)을 연결할 수 있다.
* "메인대표글꼴", "후보글꼴" (후보제한없음)
* 후보글꼴은 메인글꼴과 모양이 비슷한 글꼴로 연결해야 한다. 
* 글꼴이름에 한글이나 공백이 있으면 큰따옴표가 필요하다. 
## font-size
* 웹 글꼴 평균 16px 
* 사용 단위 px, %, em, rem 
* 절대값 : px, 상대값: %, em, rem(권장)
# 선택자 우선 순위
* #아이디(3) > .클래스(2) > 태그(1)
1. 다음 중 우선 순위가 가장 높고 낮은 선택자는?
* `#box .a .b .p {}` > 3+2+2+1 = 8
* `#box #a .b .p {}` > 3+3+2+1 = 9
* `#wrap #box .a {}` > 3+3+2 = 8
* `#wrap .a .b p {}` > 3+2+2+1 = 8
2. 다음 중 우선 순위가 가장 높고 낮은 선택자는?
* `#top .a .p {}` 3 + 2 + 2 = 7
* `#top .a #p {}` 3 + 2 + 3 = 8
* `.contents .h1 .p {}` 2 + 2 + 2 = 6
* `.contents .h1 .a p {}` 2 + 2 + 2 + 1 = 7
## color
* 영문명 직접 입력 ex) 테스트용으로 주로 밝은색을 사용한다. 
* aqua, lime, yellow, coral, ...
* 헥사코드 입력 최소값0 ~ 최대값f RGB 코드 기준 
* RGB 웹 색상 기준으로 색상을 섞을 수록 밝아진다. 
* #Hex #000000 == #000, #FF00CC => F0C
* rgba(red, green, blue, alpha) *최대색상 255
## box css
### display
* `block, inline, inline-block`
* 특정 태그가 화면에 어떻게 표시될지 지정하는 속성 
* `block` : 새로운 행, 크기, 여백 인식 
* `inline` : 내용만큼 크기 인식(그 외 크기인식불가능)
* `inline-block` : 내용만큼 크기인식(크기 추가 설정 가능), 옆으로 정렬 
### box-sizing
* `box-sizing:border-box`
* 요소의 너비와 높이를 계산할 때 테두리, 여백 (padding)까지 포함해서 계산하는 속성 
* 속성 미적용 시 : w100+f100+padding-top20 = 100x120
* 속성 적용 시 : w100+f100+padding-top20 = 100x100
### width, height
* 요소의 너비와 높이 
* 절대값px, 상대값%, 화면 상대값 vw, vh
* 상대값 처리는 0~100% 사이 값만 사용한다. 
## text align
* `부모에 상속개념`으로 text-align을 적용했을 때 그 `자식` 또는 `자손`이 `인라인인 경우`만 정렬을 적용한다.
* (css에서 선택자를 쓸 때 같은 크기나 글씨나 공통된 태그들을 적용할 때 최대한으로 공통된 선택자들을 찾아서 묶어주는 연습을 해야됨)
## form 요소와 속성 
## `<form actopn="#" method=""></form>`
* action : 
* method : 
### `<input type="" name="">`
* type : 속성은 입력양식/ 선택&목록 컨트롤 양식 종류에 따라 의미가 달라짐 
* 입력양식 :type-> text, password, tel, url, email, textarea등..
* 선택양식 :checkbox, radio, option, select 등이 있음 
* name : 서버(action)전송 시 입력한 데이터 구분 명칭
* readonly : 읽기 전용 설정 
* autofocus, autocomplete : 
* value : 미리 제시된 텍스트(활성화 시 제거안됨)
* placeholder : 미리 제시된 텍스트(활성화 시 제거됨)
* value와 placeholder의 차이점 : value는 검색란에 미리 제시된 텍스트가 있는데 사용자가 검색을 할 때 제거가 되지 않지만 placeholder는 사용자가 검색 하면서 활성화가 되면 제거가 된다. 
* maxlength : 최대글자 수 지정. 미리 사용자가 몇글자를 써도 되는지 제시를 해주는 태그임
### `<textarea></textarea>`
* rows, cols : rows는 세로열, cols는 가로열이고 rows에 예를 들어 5를 쓴다면 5문단 쓸 수 있게 미리 나와주고 세로열도 마찬가지 이므로 100을 쓴다면 그 만큼의 크기로 나온다. 
* 사용용도 및 주의사항 : rows, cols를 쓸 때 보통 가로,세로의 길이를 정확하게 알 수 없으므로 보통 css에서 처리를 한다. 
### input의 입력양식과 선택양식
* text, url 등의 사용자가 직접입력가능한 입력양식
* radio 등의 사용자의 입력이 아닌 선택으로 들어가는 선택양식
* `name` : 입력양식(데이터구분용), 선택양식(데이터구분(개별데이터x, 그룹데이터구분용))
* `value` : 입력양식(초기값), 선택양식(개별데이터구분용)
## CSS Layout
### float, flex
* `float` : 형제 관계에 해당하는 block or inline tag 왼쪽, 오른쪽 정렬할 때 사용 
* 예 : ul-li*3개 정렬 `ul li {float:left;}`
* `flex` : 정렬하고자 하는 아이템의 부모한테 flex를 먼저 설정한다. 
* 예 : ul-li*3개 정렬 `ul {display:flex;}`
* flex 설정 시 **기본값** : 메인축(수평) 교차축 (수직)
* `display:flex;` : 정렬대상의 부모 설정 속성값, 설정 시 해당 부모 기준 자식까지(자손x) flexible box layout으로 처리하겠다라는 말임 
## flex의 기초개념 알기
* 정렬대상의 부모를 `container`라고 함
* 실제 내가 정렬하고자 하는 대상을 item이라고 함
## 메인축과 교차축
* 메인축(main_axis) : 아이템이 정렬된 방향
* 교차축(cross_axis) : 아이템이 교차된 방향
### flex-direction
* `container(부모)에 적용하는 속성`으로 container안의 item의 메인축 방향 즉 아이템의 정렬방향을 설정한다. 
* `flex-direction:row` : 왼쪽 -> 오른쪽 수평축 (기본값)
* `flex-direction:row-reverse` : 오른쪽 -> 왼쪽
* `flex-direction:column-reverse` : 아래 -> 위
### flex-wrap
* `container에 적용하는 속성`으로 container내부 items 줄바꿈처리를 설정한다. 
* `flex-wrap:wrap` : 기본값(자동 줄바꿈) ex) 1 2 3
* `flex-wrap:wrap-reverse` : 행 기준 역방향으로 자동 줄바꿈 처리
* `flex-wrap:nowrap` : 줄바꿈하지 않음 (한 줄 처리) 가변너비에 따라 자동으로 % 크기로 변경
### flex-flow
* `container에 적용하는 속성`으로 flex-direction과 flex-wrap을 묶음으로 처리할 수 있음 
* `flex-direction:column + flex-wrap:nowrap`일 경우(아래)
* `flex-flow:column nowrap` 이라고 작성 가능 
### justify-content
* `container에 적용하는 속성`으로 메인축의 정렬방법으로 설정함
* `justify-content:flex-start` : items의 시작점 container의 시작점으로 정렬
* `justify-content:flex-end` : items의 시작점 container의 끝점으로 정렬
* `justify-content:center` : items을 메인축 기준 container에서 가운데 정렬
* `justify-content:space-between` : items을 container의 start,end 양끝 items을 배치하고 나머지는 고르게 정렬
* `justigy content:space-around` : items을 container안에서 균등한 여백을 포함하여 정렬
### align-content
* `container에 적용하는 속성`으로 교6차축의 아이템이 2줄 이상일 경우 정렬방법임
* -flex-wrap:wrap적용한 상태로 확인하세요
* `align-content:stretch` : 기본값(교차축 기준으로 아이템 늘리기)
* `align-content:flex-start` : container의 start지점 기준 item 정렬
* `align-content:flex-end` : container의 end지점 기준 item 정렬
* `align-content:center` : container의 가운데 위치 기준 item 정렬
* `align-content:space-between` : container의 start,end에 양쪽 끝 맞추고 나머지 item 균등하게 정렬
* `align-content:space-around` : container에서 모든 item 균등하게 정렬
### align-items
* `container에 적용하는 속성`으로 교차축의 아이템이 1줄 일 경우 정렬방법임 (한줄이니까between, around는 적용이 안됨)
* `align-items:stretch` : (기본값) 교차축 방향 시작지점에 맞춰서 정렬(start와 거의 차이 없음)

* `align-items:flex-start` : 교차축 기준 container의 시작지점에 맞춰서 정렬(왼쪽 / 위)
* `align-items:flex-end` : 교차축 기준 container의 종료지점에 맞춰서 정렬(오른쪽 / 아래)
* `align-items:center` : 교차축 기준 container의 가운데 지점에 맞춰서 정렬(수직중앙, 수평중앙)
* `align-items:baseline` : 교차축 기준 container의 시작지점에 맞춰서 정렬(왼쪽 / 위)
### align-self
* `item에 적용하는 속성`으로 container에 적용하는 align-items보다 우선순위가 높음
* flex box의 교차축을 정렬합니다. 
* `align-self:flex-start` : 교차축 기준 container의 start 시작 위치 (top or left)
* `align-self:flex-end` : 교차축 기준 container의 end 종료 위치 (bottom or right)
* `align-self:center` : 교차축 기준 container의 center중심 위치(center, middle)
* `align-self:baseline` : 교차축 기준 container의 baseline 위치(내용 크기에 따라 다름 (기본은 start동일))
### order
* `item에 적용하는 속성`으로 아이템의 정렬순서 설정 (단위x)
* `order:-1` : ex)예시 숫자 중 가장 작은 수로 처번째 정렬된다. 
* `order:0` : ex)예시 숫자 중 두번째 큰 수로 두번째 정렬된다. 
* `order:1` : ex)예시 숫자 중 가장 큰수로 세번째 정렬된다. 
### flex
* `item에 적용하는 속성`으로 증가/감소/기본의 묶음 속성임
