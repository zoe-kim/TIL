# object-fit

object-fit 속성은 `img` 나 `video` 태그와 같은 콘텐츠의 크기를 어떤 방식으로 조절해 영역에 맞출 것인지 지정한다. (background-size 속성과 비슷함) 콘텐츠는 어떻게 틀어질지 모르는 예민한 요소라, 직접적으로 스타일을 넣기보다는 부모 요소로 감싼 뒤 object-fit 속성 및 스타일 넣기를 권장!

<br>

## 💡 요약

<figure>
    <table>
        <thead>
            <tr>
                <th>값</th>
                <th>정의</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>contain</td>
                <td>콘텐츠의 가로세로비 유지 O, 영역에 콘텐츠 전체가 들어가도록 크기를 조절한다. (여백 보일 수 있음)</td>
            </tr>
            <tr>
                <td>cover</td>
                <td>콘텐츠의 가로세로비 유지 O, 일부를 잘라 영역을 가득 채운다.</td>
            </tr>
            <tr>
                <td>fill (기본값)</td>
                <td>콘텐츠의 가로세로비 유지 X, 강제로 늘려 영역을 가득 채운다.</td>
            </tr>
        </tbody>
    </table>
</figure>