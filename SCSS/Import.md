# @import

파일 불러오기. main.scss에 선언해 다른 .scss 파일들을 인식하도록 불러와 한 번에 css로 컴파일하는 방식으로 사용한다.

<br>

## 💡 선언 방법

* 언더바(_), 확장자는 생략 가능
* 변수 관련 .scss는 항상 **최상단**에 선언
  ```scss
  @import './constants/colors';
  @import './constants/typography';
  @import './constants/breakpoints';

  @import './base/fonts';
  @import './base/normalize';
  @import './base/reset';

  @import './mixins/text-style';
  @import './mixins/responsive';
  @import './mixins/positions';
  ```