# SCSS 초기 설정

SASS : 문법적으로 짱 멋진 스타일시트(Syntactically Awesome Style Sheets). CSS를 구조화하여 표현할 수 있다.<br>
**SCSS** : SASS의 3버전에서 등장한 언어로, 기존 구문에 비해 좀 더 CSS 코드와 유사한 형태를 띄고 있어 각광 받는 전처리기 언어이다.

<br>

## 💡 컴파일
SCSS 코드 자체로는 웹에서 돌아가지 않고, CSS로 컴파일 해주어야 한다.
<br>

### **node-sass**

1. **[Node.js](https://nodejs.org/en/download/)를 LTS(= 최신 장기 지원 버전)으로 설치한다.**
2. **터미널에 `node -v`, `npm -v` 입력해 설치 확인**
3. **터미널에 `npm init -y` 입력**<br>
node 프로그램을 시작하는 명령어로, package.json (해당 node 프로그램에 대한 기본 정보를 담고 있는 파일) 생성을 돕는다.
4. **터미널에 `npm i node-sass` 입력해 [node-sass](https://www.npmjs.com/package/node-sass)를 설치한다.**<br>
node_modules (node-sass에 필요한 코드 모음) 폴더가 생성되고, package.json "dependencies" 항목에 node-sass가 추가된다.<br>
5. **package.json "scripts" 항목에 `"node-sass" : "node-sass"` 추가하여 명령어 등록**<br>
`npm run node-sass` 명령어를 실행할 수 있다. (내용이 없어서 에러 뜸. 하지만 좋은 에러.)
6. **package.json "scripts" 항목에 `"sass" : "node-sass styles/main.scss style.css"` 추가하여 출발 및 목적지 경로 지정**<br>
`npm run sass` 명령어를 실행할 수 있다. [node-sass](https://www.npmjs.com/package/node-sass)에서 Command Line Interface 검색해서 Example 복붙 후, 경로 수정한다.
7. **위 항목에 `-w` 추가하여 `"sass" : "node-sass -w styles/main.scss style.css"` 로 수정**<br>
[node-sass](https://www.npmjs.com/package/node-sass) options으로, SCSS를 실시간 감시하여 저장 시 자동으로 컴파일한다.
8. **위 항목에 `-r` 추가하여 `"sass" : "node-sass -wr styles/main.scss style.css"` 로 수정**<br>
[node-sass](https://www.npmjs.com/package/node-sass) options으로, SCSS를 재귀적으로 감시하여 하위 디렉토리까지 찾아서 컴파일한다.
9. **위 항목에 `--source-map` 추가하여 `"sass" : "node-sass -wr --source-map true styles/main.scss style.css"` 로 수정**<br>
[node-sass](https://www.npmjs.com/package/node-sass) options으로, 컴파일 이후에도 브라우저에서 SCSS를 참조할 수 있게 정보를 맵핑해준다.<br>
(boolean 값이나, .css.map에 대한 목적지를 함께 작성해야 함.)
10. **터미널에 `npm run sass` 입력하면 컴파일 완료!**
<br>

### **Live Sass Compiler**

1. **VSC 확장에서 Live Sass Compiler 검색하여 설치**
2. **settings.json 파일 수정**<br>
설정 창에서 우측 상단 '설정 열기(JSON)' 아이콘 클릭
```json
"liveSassCompile.settings.formats": [
  {
    "format": "expanded",  // .css 스타일 양식 (하단 표 참고)
    "extensionName": ".css",
    "savePath": "/css"  // .css 저장 경로 지정
  }
],
"liveSassCompile.settings.generateMap": false  // .map 파일 생성 여부 지정
```
<figure>
  <table>
      <thead>
          <tr>
              <th style='text-align:center;'>종류</th>
              <th style='text-align:center;'>설명</th>
              <th style='text-align:center;'>예시</th>
          </tr>
      </thead>
      <tbody>
          <tr>
              <td style='text-align:center;'>nested</td>
              <td style='text-align:center;'>컴파일 기본값, 미지정시 사용</td>
              <td>h1{<br>
margin: 20px; }</td>
          </tr>
          <tr>
              <td style='text-align:center;'>expanded</td>
              <td style='text-align:center;'>줄바꿈, 계층구조로 처리</td>
              <td>h1{<br>
margin: 20px;<br>
}</td>
          </tr>
          <tr>
              <td style='text-align:center;'>compact</td>
              <td style='text-align:center;'>줄바꿈 없이 한 줄로 적용</td>
              <td>h1{margin: 20px;}</td>
          </tr>
          <tr>
              <td style='text-align:center;'>compressed</td>
              <td style='text-align:center;'>불필요한 공백 모두 제거</td>
              <td>h1{margin:20px;}h2{color:red;}</td>
          </tr>
      </tbody>
  </table>
</figure>

3. **VSC 하단 상태표시줄에 'Watch Sass' 버튼 누르면 컴파일 완료!**
<br>

## 💡 SCSS 린터
문법적 실수 등을 감시하여, 일관성 있는 코드를 작성할 수 있도록 도와주는 Automatic fix
<br>

### **scss-lint**

1. **VSC 확장에서 scss-lint 검색하여 설치**
2. **프로젝트 폴더에 .scss-lint.yml 파일 만들고 [raw file](https://gist.github.com/zoe-kim/edb69e9438c922ad7f413461eb25fddb) 붙여넣기 (출처 : 김버그님 gist)**
3. **실행 오류 나면 컴퓨터에 Ruby Sass 설치되어 있는지 확인하기!!**<br>
3-1. Windows : [ruby-on-windows](https://phoenixnap.com/kb/install-ruby-on-windows-10) 설치 / MacOS : [Homebrew](https://brew.sh/) 설치하고, 터미널에 `brew install ruby` 입력<br>
3-2. 터미널에 `gem install scss_lint` 입력하여 scss_lint 설치

<br>
