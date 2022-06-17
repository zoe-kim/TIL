# @mixin

스타일시트 전체에서 재사용할 CSS 선언 그룹을 정의하는 기능. @mixin은 재사용할 내용을 선언, @include는 @mixin에 정의된 내용을 호출한다.

<br>

## 💡 기본 문법


```scss
@mixin mixin-name {...}
```
```scss
// 선언
@mixin text-style {
  font-size: $font-size;
  line-height: $line-height;
  letter-spacing: $letter-spacing;
}

// 호출
p {
  @include text-style;
}
```

<br>

## 💡 인자 사용

```scss
@mixin mixin-name($arg1, $arg2, ...) {...}
```
```scss
// 선언
@mixin text-style($margin, $color) {
  margin: $margin;
  color: $color;
}

// 호출
p {
  @include text-style(20px 0px, blue);
}
```

<br>

## 💡 인자 사용 + 특정 인자 기본값 설정

인자를 사용하고, 특정 인자에는 기본값을 설정한 예제이다. 조건에 따라 호출 시 인자에 대한 값을 정해주지 않으면 기본값을 사용하거나, 아예 적용하지 않는다.

```scss
// 선언
@mixin text-style($margin, $color: blue) {
  margin: $margin;
  color: $color;
}

// 호출
p {
  @include text-style(20px 0px);  // 인자에 대한 값을 정해주지 않으면 기본값 사용
}
```
```scss
// 선언
@mixin text-style($margin, $color: false) {
  margin: $margin;

  // 유효성 검사 (color 값이 맞는지)
  @if (type-of($color) == color) {
    color: $color;
  }
}

// 호출
p {
  @include text-style(20px 0px);  // 인자에 대한 값을 정해주지 않으면 mixin 미적용
}
```

<br>

## 💡 @content

선언된 mixin에 @content가 포함되어 있다면, 호출 시 해당 부분에 원하는 스타일 블록을 입력할 수 있다. 이 방식을 사용하여 기존의 mixin이 가지고있는 기능에 선택자나 속성 등을 추가할 수 있다.

```scss
// 선언
@mixin text-style($margin) {
  margin: $margin;
  @content;
}

// 호출
@include text-style(20px 0px) {
  color: blue; // mixin에 스타일 추가하여 사용
}
```
