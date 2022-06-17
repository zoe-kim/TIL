# 속성 선택자 (Attribute Selector)

속성 선택자를 사용하면 특정 속성이나 특정 속성 값을 가지고 있는 HTML 요소를 선택할 수 있다.

<br>

## 💡 기본 속성 선택자
 
* **[attribute]** : 해당 속성을 가진
* **[attribute="value"]** : 해당 속성을 갖고, 그 값이 value인


<br>

## 💡 문자열 속성 선택자

* **[attribute~="value"]** : 해당 속성을 갖고, 그 값 중에 정확히 value가 **포함되는**
  ```scss
  div[class~="Last"]{color: red;} // "Last", "Last name"(O)
                                  // "Last-name", "Lastname"(X)
  ```
* **[attribute`*`="value"]** : 해당 속성을 갖고, 그 값이 value를 **포함하기만 하면**
  ```scss
  div[class$="Last"]{color: red;} // "Last", "Last name", "Last-name", "nameLast"(O)
  ```
* **[attribute|="value"]** : 해당 속성을 갖고, 그 값이 value-로 **시작하는**
  ```scss
  div[class|="Last"]{color: red;} // "Last", "Last-name"(O)
                                  // "Last name", "Lastname"(X)
  ```
* **[attribute^="value"]** : 해당 속성을 갖고, 그 값이 value로 **시작하기만 하면**
  ```scss
  div[class^="Last"]{color: red;} // "Last", "Last name", "Last-name", "Lastname"(O)
  ```
* **[attribute$="value"]** : 해당 속성을 갖고, 그 값이 value로 **끝나기만 하면**
  ```scss
  div[class$="Last"]{color: red;} // "Last", "name Last", "name-Last", "nameLast"(O)
  ```


<br>

## 💡 요약

<figure>
    <table>
        <thead>
            <tr>
                <th>선택자</th>
                <th>기능</th>
                <th>공백</th>
                <th>하이픈(-)</th>
                <th>언더바(_)</th>
                <th>합성어</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>[attribute]</td>
                <td>[속성명]</td>
                <td style='text-align:center;'>X</td>
                <td style='text-align:center;'>X</td>
                <td style='text-align:center;'>X</td>
                <td style='text-align:center;'>X</td>
            </tr>
            <tr>
                <td>[attribute = "value"]</td>
                <td>[속성명 + 속성값]</td>
                <td style='text-align:center;'>X</td>
                <td style='text-align:center;'>X</td>
                <td style='text-align:center;'>X</td>
                <td style='text-align:center;'>X</td>
            </tr>
            <tr>
                <td>[attribute ~= "value"]</td>
                <td>[속성명 + 특정 문자 들어간 속성값]</td>
                <td style='text-align:center;'>O</td>
                <td style='text-align:center;'>X</td>
                <td style='text-align:center;'>X</td>
                <td style='text-align:center;'>X</td>
            </tr>
            <tr>
                <td>[attribute *= "value"]</td>
                <td>[속성명 + 특정 문자 들어간 속성값]</td>
                <td style='text-align:center;'>O</td>
                <td style='text-align:center;'>O</td>
                <td style='text-align:center;'>O</td>
                <td style='text-align:center;'>O</td>
            </tr>
            <tr>
                <td>[attribute |= "value"]</td>
                <td>[속성명 + 접두사로 시작하는 속성값]</td>
                <td style='text-align:center;'>X</td>
                <td style='text-align:center;'>O</td>
                <td style='text-align:center;'>X</td>
                <td style='text-align:center;'>X</td>
            </tr>
            <tr>
                <td>[attribute ^= "value"]</td>
                <td>[속성명 + 접두사로 시작하는 속성값]</td>
                <td style='text-align:center;'>O</td>
                <td style='text-align:center;'>O</td>
                <td style='text-align:center;'>O</td>
                <td style='text-align:center;'>O</td>
            </tr>
            <tr>
                <td>[attribute $= "value"]</td>
                <td>[속성명 + 접미사로 끝나는 속성값]</td>
                <td style='text-align:center;'>O</td>
                <td style='text-align:center;'>O</td>
                <td style='text-align:center;'>O</td>
                <td style='text-align:center;'>O</td>
            </tr>
        </tbody>
    </table>
</figure>