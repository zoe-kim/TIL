# @media 쿼리

미디어 쿼리를 사용하면 웹 페이지에 접속하는 기기 사이즈에 따라 알맞은 형태로 스타일이 조정되어, 반응형 웹을 제작할 때 유용하다.

<br>

## 💡 사용 방법

* **모바일 우선** : **min-width** 사용 (작은 가로폭 -> 큰 가로폭 순서)
* **데스크탑 우선** : **max-width** 사용 (큰 가로폭 -> 작은 가로폭 순서)

```scss
// 기본 문법
@media (media-type) and (media-feature-rule) {...}
```
```scss
// 예시

// MOBILE (<768px) *********************************************************
.container {
  width: 100%;
  padding: 0 $sm-margin;

  // TABLET (>=768px) ********************************************************
  @media screen and (min-width: 768px) {
    padding: 0 $md-margin;
  }

  // DESKTOP (>=1200px) ******************************************************
  @media screen and (min-width: 1200px) {
    padding: 0;
  }
}
```
<br>

## 💡 매체 유형 (media-type)

<figure>
    <table>
        <thead>
            <tr>
                <th style='text-align:center;'>매체 유형</th>
                <th style='text-align:center;'>설명</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td style='text-align:center;'>all</td>
                <td style='text-align:center;'>모든 매체에 사용함.</td>
            </tr>
            <tr>
                <td style='text-align:center;'>print</td>
                <td style='text-align:center;'>프린터 기기에 사용함.</td>
            </tr>
            <tr>
                <td style='text-align:center;'>screen</td>
                <td style='text-align:center;'>컴퓨터, 스마트폰 등 스크린이 있는 매체에 사용함.</td>
            </tr>
            <tr>
                <td style='text-align:center;'>speech</td>
                <td style='text-align:center;'>웹 페이지를 읽어주는 스크린 리더에 사용함.</td>
            </tr>
        </tbody>
    </table>
</figure>

<br>

기존에는 screen만 사용해왔으나, 스크린리더까지 고려해서 all을 사용하는 것이 좋을 것 같다.
```scss
@media (min-width: 700px) {background-color: yellow;}  // media-type 기본값이 all이라 생략 가능
```
