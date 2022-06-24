# 내장함수

SASS에서 기본적으로 제공하는 내장 함수. 정의된 모든 함수는 [sass-lang.com](https://sass-lang.com/documentation/modules)에서 확인 가능하다.

<br>

## 💡 색상 함수 (RGB / HSL / Opacity)
 
* `mix($color1, $color2)` : 두 개의 색을 섞는다.
* `lighten($color, $amount)` : 더 밝은색을 만든다.
* `darken($color, $amount)` : 더 어두운색을 만든다.
* `saturate($color, $amount)` : 색상의 채도를 올린다.
* `desaturate($color, $amount)` : 색상의 채도를 낮춘다.
* `grayscale($color)` : 색상을 회색으로 변환한다.
* `invert($color)` : 색상을 반전시킨다.
* `rgba($color, $alpha)` : 색상의 투명도를 변경한다.
* `opacify($color, $amount)` / `fade-in($color, $amount)` : 색상을 더 불투명하게 만든다.
* `transparentize($color, $amount)` / `fade-out($color, $amount)` : 색상을 더 투명하게 만든다.

<br>

## 💡 문자 함수 (String)
 
* `unquote($string)` : 문자에서 따옴표를 제거한다.
* `quote($string)` : 문자에 따옴표를 추가한다.
* `str-insert($string, $insert, $index)` : 문자의 index번째에 특정 문자를 삽입한다.
* `str-index($string, $substring)` : 문자에서 특정 문자의 첫 index를 반환한다.
* `str-slice($string, $start-at, [$end-at])` : 문자에서 특정 범위의 문자를 추출한다.
* `to-upper-case($string)` : 문자를 대문자로 변환한다.
* `to-lower-case($string)` : 문자를 소문자로 변환한다.

<br>

## 💡 숫자 함수 (Number)
 
* `percentage($number)` : 숫자(단위 무시)를 백분율로 변환한다.
* `round($number)` : 정수로 반올림한다.
* `ceil($number)` : 정수로 올림한다.
* `floor($number)` : 정수로 내림(버림)한다.
* `abs($number)` : 숫자의 절댓값을 반환한다.
* `min($numbers…)` : 숫자 중 최솟값을 찾는다.
* `max($numbers…)` : 숫자 중 최댓값을 찾는다.
* `random()` : 0 ~ 1 사이의 난수를 반환한다.

<br>

## 💡 List 함수

* `length($list)` : List의 개수를 반환한다.
* `nth($list, $n)` : List에서 n번째 값을 반환한다.
* `set-nth($list, $n, $value)` : List에서 n번째 값을 다른 값으로 변경한다.
* `join($list1, $list2, [$separator])` : 두 개의 List를 하나로 결합한다.
* `zip($lists…)` : 여러 List들을 하나의 다차원 List로 결합한다.
* `index($list, $value)` : List에서 특정 값의 index를 반환한다.


<br>

## 💡 Map 함수
key와 value가 한 쌍을 이루는 자료 구조. (json 형태)

* `map-get($map, $key)` : Map에서 특정 key의 value를 반환한다.
  ```scss
  // map 선언
  $flex-map: (
    start: flex-start,
    end: flex-end,
    between: space-between,
    around: space-around,
    stretch: stretch,
    center: center,
  );

  // map-get 함수 선언
  @function _get-flex-value($key) {
    @return map-get($flex-map, $key)
  }

  // mixin 활용
  @mixin flexbox($jc: center, $ai: center) {
    display: flex;
    align-items: _get-flex-value($ai);
    justify-content: _get-flex-value($jc);
  }
  ```
* `map-merge($map1, $map2)` : 두 개의 Map을 병합하여 새로운 Map를 만든다.
* `map-keys($map)` : Map에서 모든 key를 List로 반환한다.
* `map-values($map)` : Map에서 모든 value를 List로 반환한다.

<br>

## 💡 관리 함수

* `variable-exists(name)` : 변수가 현재 범위에 존재하는지 여부를 반환한다. (인수는 $없이 변수의 이름만 사용한다.)
* `unit($number)` : 숫자의 단위를 반환한다.
* `unitless($number)` : 숫자에 단위가 있는지 여부를 반환한다.
* `comparable($number1, $number2)` : 두 개의 숫자가 연산 가능한지 여부를 반환한다.
