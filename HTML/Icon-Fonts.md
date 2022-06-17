# Icon Fonts

아이콘을 폰트와 같은 벡터 방식으로 웹사이트에 쉽게 적용할 수 있다. 크기를 늘리든 줄이든 상관없이 선명하고, CSS에서 color 속성으로 색상 변경을 할 수 있는 등의 장점이 있다.

<br>

## 💡 아이콘 폰트 변환 사이트

[IcoMoon](https://icomoon.io/app/#/select)

<br>

## 💡 이용 방법
 
1. Import Icons 누르고 .svg 파일 한번에 업로드
2. 우측 메뉴 열고 Select All 선택
3. 우측 하단 Generate Font 누르고 개별 이름 변경 (영어 소문자 권장)
4. 우측 하단 Download 옆 설정 -> 폰트 및 공통 클래스 명 설정, CSS Selector에서 Use i 체크
5. Download 후, 프로젝트 폴더에 fonts 옮겨놓기
6. 다운 받은 style.css 내용 복사, 프로젝트 폴더에 _font.scss 파일 만들어 붙여넣고 내부 폰트 경로 재설정
7. 폰트 형식 뒤에 ?to8179와 같이 붙는 이상한 태그 지우기
8. 필요없는데 에러뜨는 부분은 주석 처리
```scss
  // src: url('fonts/tomorrow-house.eot?to8179'); -> 경로 재설정 및 태그 삭제
  src: url('./assets/fonts/tomorrow-house.eot');

  // speak: never; -> 주석 처리
```