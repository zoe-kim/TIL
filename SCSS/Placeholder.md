# % (Placeholder 선택자)

Placeholder 선택자는 단독으로 사용하면 CSS에 컴파일 되지 않고, 변수를 사용하듯 원하는 요소에 불러와서 사용할 수 있다. <br>
자주 쓰는 요소들을 UI components로 만들 때 사용한다. **%** 문자와 함께 선언하고, **@extend**를 통해 호출한다.

<br>

## 💡 기본 문법

```scss
%placeholder-name {...}
```
```scss
// 선언
.box, %box-style {
  border: 1px solid #333;
  background: #fff;
}

// 호출
.box2{
  @extend %box-style;
}
```

<br>

## 💡 @mixin과 차이점?

* **@mixin** : 연관성 없는 선택자의 중복 코드를 막기 위해 사용.
  ```scss
  @mixin site_color {
    color: #f00;
  }

  // 서로 연관성이 없어, 수백줄 이상 떨어져 있을 클래스들
  .main_conatiner {
    @include site_color;
  }
  .view_container {
    @include site_color;
  }
  .detail_container {
    @include site_color;
  }
  ```
  * CSS 컴파일 결과
    ```scss
    .main_conatiner {color: #f00;}
    .view_container {color: #f00;}
    .detail_container {color: #f00;}
    ```

<br>

* **%(placeholder)** : 선택자 간의 연관성 있는 규칙을 만들기 위해 사용. (+ 인자 값 사용 X)
  ```scss
  %btn {
    width: 100px;
    height: 80px;
  }

  // 같은 버튼이지만, 종류가 다른 버튼들
  .btn_success {
    @extend %btn;
    color: green;
  }
  .btn_danger {
    @extend %btn;
    color: red;
  }
  .btn_warning {
    @extend %btn;
    color: orange;
  }
  ```
    * CSS 컴파일 결과
      ```scss
      .btn_success, .btn_danger, .btn_warning {width: 100px; height: 80px;}
      .btn_success {color: green;}
      .btn_danger {color: red;}
      .btn_warning {color: orange;}
      ```
