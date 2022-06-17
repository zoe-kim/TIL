# Font Smoothing

브라우저에 표현되는 텍스트가 렌더링 될 때 부드럽게 표현된다.

<br>

## 💡 이용 방법
 
1. 스타일 초기화 파일에서 전체 선택자(*)에 선언
```scss
* {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
```