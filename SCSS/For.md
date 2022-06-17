# @for 반복문

클래스 스타일 또는 값을 일정하게 변화하면서 일정 횟수 반복하여 사용할 수 있는 문법. 자바스크립트의 for(반복문)와 비슷하다. @for 는 through를 사용하는 형식과 to를 사용하는 형식으로 나누어진다.

<br>

## 💡 선언 방법

* **through** : 시작부터 종료 조건까지 반복
  ```scss
  // 기본 문법
  @for $변수 from 시작 through 종료 {...};

  // 예시 (1~3까지 반복)
  @for $i from 1 through 3 {
      .through:nth-child(3n + #{$i}) {
          width: 50px * $i
      }
  }
  ```

* **to** : 시작부터 종료 조건 직전까지 반복
  ```scss
  // 기본 문법
  @for $변수 from 시작 to 종료 {...};

  // 예시 (1~2까지 반복)
  @for $i from 1 to 3 {
      .to:nth-child(3n + #{$i}) {
          width: 50px * $i
      }
  }
  ```