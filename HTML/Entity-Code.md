# 엔티티 코드 (Entity Code)

Html 문서에서 특수문자를 입력하기 위해 사용하는 코드이다. 요즘은 UTF-8을 주로 이용하기 때문에 특수문자가 깨지지 않지만, W3C는 특수문자를 오류로 인식하기 때문에 엔티티 코드로 작성하는 것이 좋다.

<br>

## 💡 사용 빈도수가 높은 특수문자

<figure>
    <table>
        <thead>
            <tr>
                <th>특수문자</th>
                <th>문자식 표현(Entity Code)</th>
                <th>숫자식 표현(Entity Number)</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td style='text-align:center;'><</td>
                <td style='text-align:center;'>&amp;lt;</td>
                <td style='text-align:center;'>&amp;#8249;</td>
            </tr>
            <tr>
                <td style='text-align:center;'>></td>
                <td style='text-align:center;'>&amp;gt;</td>
                <td style='text-align:center;'>&amp;#8250;</td>
            </tr>
            <tr>
                <td style='text-align:center;'>©</td>
                <td style='text-align:center;'>&amp;copy;</td>
                <td style='text-align:center;'>&amp;#169;</td>
            </tr>
            <tr>
                <td style='text-align:center;'>"</td>
                <td style='text-align:center;'>&amp;quot;</td>
                <td style='text-align:center;'>&amp;34;</td>
            </tr>
            <tr>
                <td style='text-align:center;'>&</td>
                <td style='text-align:center;'>&amp;amp;</td>
                <td style='text-align:center;'>&amp;38;</td>
            </tr>
            <tr>
                <td style='text-align:center;'>(공백)</td>
                <td style='text-align:center;'>&amp;nbsp;</td>
                <td style='text-align:center;'>&amp;160;</td>
            </tr>
        </tbody>
    </table>
</figure>
  
<br>

## 💡 엔티티 코드 참고 사이트

[dev.w3.org](https://dev.w3.org/html5/html-author/charref)
<br>
[entitycode.com](https://entitycode.com/)