# TIL
    ✍🏻 Today Zoe Learned

<br>

## HTML
```html
<title>전기히터 &gt; 캠핑/가정용 400W 미니멀 전기히터 VO-HT015 (안전장치기능탑재) | 내일의 집</title>
```
- 특수문자는 브라우저가 코드로 인식할 수 있어서, html entity code 사용 권장

<br>

## CSS
> CSS 초기화
1) Normalize.css (https://necolas.github.io/normalize.css/) 에서 다운로드
2) 프로젝트 폴더에 _normalize.scss 파일 만들어서 raw파일 붙여넣기
3) 추가 커스텀 reset -> _reset.scss 만들어서 직접 작성
<br>

> Grid System
- unit : 기둥 하나의 width 값
- gutter : unit 사이의 간격
- column : unit + gutter (unit 양 옆을 1/2 gutter가 감싼 형태)
- container : 모든 column을 묶은 형태
- margin : container 양쪽 끝에 붙는 여백

<br>

## SCSS
> 변수 선언
1) $ 붙이고 값 넣기 -> $hongsi : 1;
2) 변수명 조건 : 숫자로 시작할 수 없음, 소문자 및 대시(-) 사용 권장
3) 값 조건 : CSS의 property에 사용되는 모든 value -> $hongsi : color 20ms ease-in-out;과 같이 긴 내용도 가능
<br>

> @import
1) main.scss가 다른 .scss들을 인식하도록 불러옴
2) 언더바(_), 확장자는 생략 가능
3) 변수 관련 .scss는 항상 최상단에 선언
```scss
@import './constants/colors';

@import './base/fonts';
@import './base/normalize';
@import './base/reset';
```

<br>

## ETC
> Favicon 만들기
1) 설정할 이미지 .svg로 출력
2) Favicon Generator (https://realfavicongenerator.net/) 에 업로드
3) 패키지 다운로드 후, 프로젝트 폴더 root(최상위 디렉토리)에 옮겨놓기
4) 링크 태그들 title 아래에 붙여넣기
<br>

> 구글 웹폰트 적용
1) fonts.google.com 에서 링크로 가져오기
2) css 링크 위에 선언할 것
<br>

> 아이콘 폰트 만들기
1) https://icomoon.io/app/#/select 
2) Import Icons 누르고 .svg 파일 업로드
3) 우측 메뉴 열고 Select All
4) 우측 하단 Generate Font 누르고 개별 이름 변경 (소문자)
5) 우측 하단 Download 옆 설정 -> 폰트 및 공통 클래스 명 설정, CSS Selector에서 Use i 체크
6) Download 후 프로젝트 폴더에 fonts 옮겨놓기
7) 다운 받은 style.css 내용 복사, 프로젝트 폴더에 _font.scss 파일 만들어 붙여넣고 내부 폰트 경로 재설정
<br>

> font-smoothing 속성
1) 폰트를 부드럽게 렌더링
2) CSS 초기화 전체 요소 단에 작성
```scss
* {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
```
