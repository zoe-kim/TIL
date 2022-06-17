# Grid System

페이지 콘텐츠를 논리적이고 일관성 있는 구조로 디자인할 수 있도록 돕는 그래픽 시스템이다. 개발자의 입장에서는 여러 해상도에 상관없이 안정적인 UI를 구현시키는데 사용할 수 있어, 이를 통해 유지 보수의 효율을 높일 수 있다.

<br>

## 💡 구성 요소
 
* **unit** : 기둥 하나의 width 값
* **gutter** : unit 사이의 간격
* **column** : unit + gutter (unit 양 옆을 1/2 gutter가 감싼 형태)
* **container** : 모든 column을 묶은 형태
* **margin** : container 양쪽 끝에 붙는 여백