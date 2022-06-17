# 변수 (Variable)

SCSS에서도 변수를 선언하고 사용할 수 있다. 변수를 사용하여 지정해두면 간단하게 변수 값만 변경해 모든 페이지의 스타일을 한 번에 변경해 적용할 수 있고, 모든 변수들을 _vars.scss 같은 파일에 모아서 관리할 수 있어 유지보수, 고도화에 유리하다.

<br>

## 💡 선언 방법
 
1. 변수 선언 시 아래와 같이 **`$`** 키워드를 사용한다.
```scss
$hongsi : 1;  // $변수명: 값;
```
2. 변수명은 숫자로 시작할 수 없으며, 소문자 및 대시(-) 사용 권장
3. 값에는 CSS property에 사용되는 모든 value 선언 가능하며, **`color 20ms ease-in-out;`** 과 같이 긴 내용도 가능하다.

<br>

## 💡 변수 보간법
문자열의 변수를 값으로 치환하는 것.<br>
**`#{$변수}`** 문법을 적용해야만 정상 동작하게 된다.

```scss
$widthLeft : 20px;

.column {
  width: calc(100% - $widthLeft);  // (X)에러 발생
  width: calc(100% - #{$widthLeft});  // (O)정상 동작
}
```
```scss
@mixin custom-icon($name) {
  // 생성될 스타일의 이름에도 보간법 사용
  .icon-#{$name} {
    background-image: url('/icons/#{$name}.svg');  // 파일명을 변수로 받는 경우에도 보간법 사용
  }
}
```