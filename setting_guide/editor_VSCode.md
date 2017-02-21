# Visual Studio Code



## 0. 참고링크
* 다운로드 : https://code.visualstudio.com/
* Documentation : https://code.visualstudio.com/docs
* 각종 확장 검색 : https://marketplace.visualstudio.com/VSCode






## 1. 주요 확장 모음



### View In Browser
* 브라우저 보기 : `Ctrl` + `F1`
* 브라우저 셋팅 : 파일 > 기본 설정 > 설정
  ```json
  {
  	"view-in-browser.customBrowser": "firefox"
  }

  // 브라우저 : firefox, chrome, iexplore, Safari
  // mozilla 인식되지 않고 firefox 로 인식됨
  ```
  cf) Firefox 로 파일을 열 때는 `mozilla` 또는 `firefox`로 값을 넣어줄 것




### ESLint
	문법 오류 감지



### Guides
	Tab 세로 가이드 라인



### Sass
```
Indented Sass syntax highlighting, autocomplete & snippets for VSCode
```

* Snippets
  ```
  Snippets have been reduced to a few time savers.

  var - declare a new variable
  mixin - declare a new mixin
  if - base for an @if statement
  for - base for a @for loop
  each - base for a @each loop
  while - base for a @while loop
  ```




### Color Picker

* `Alt` + `C`   `P`
* `Alt` + `C`   `Alt` + `P` 로 변경



### Document This
* "Document This" is a Visual Studio Code extension that automatically generates detailed JSDoc comments for both TypeScript and JavaScript files.
* 설명 : https://marketplace.visualstudio.com/items?itemName=joelday.docthis



##### Functionality
Supports JSDoc and Closure Compiler tags :
	@class, @description, @enum, @export, @function, @implements, @interface, @param, @private, @returns, @static, @template, @type and @memberOf.


##### Document This
`Ctrl` + `Alt` + `D` and again `Ctrl` + `Alt` + `D`
	Generates documentation for whatever the caret is on or inside of.

##### Document Everything
`Ctrl` + `Alt` + `D` and after, `Ctrl` + `Alt` + `E`
	Generates documentation for all symbols that are supported by the extension.

##### Document Everything Visible
`Ctrl` + `Alt` + `D` and after `Ctrl` + `Alt` + `V`
	Generates documentation for exported, public and protected symbols in the document.



### TabSpacer
| 단축키                    | 기능 설명             |
| ---------------------- | ----------------- |
| `Ctrl` + `Shift` + `S` | 공백을 탭으로 변경        |
| `Ctrl` + `Shift` + `T` | 탭을 공백으로 변경        |
| `Ctrl` + `Shift` + `Z` | 탭모양 - 탭/공백 토글로 지정 |







## 2. 기본설정 수정
	파일 > 기본 설정 > 설정
	setting.json 의 사용자 설정 수정
	각자 스타일로 셋팅

```json
{
	"editor.tabSize": 2,
	"editor.lineHeight": 20,
	"window.zoomLevel": 1,
	"files.trimTrailingWhitespace": true,
	"editor.wordWrap": false,
	"editor.renderWhitespace": "boundary",
	"editor.renderControlCharacters": true,
	"editor.insertSpaces": false,
	"editor.wrappingColumn": 0,
	"editor.renderIndentGuides": true,
	"editor.cursorStyle": "underline",
	"view-in-browser.customBrowser": "chrome",
	"emmet.triggerExpansionOnTab": false,
	"emmet.syntaxProfiles": {},
	
	// 언어 식별자 집합에 대해 재정의할 설정을 구성합니다.
  	// ex) tabSize를 기본 2로 하고 javascript 에서는 4로 하고 싶을 때
  	// "[javascript]": {"editor.tabSize": 4}
 	"[]": {}
}
```

* [언어별 개별설정 방법 상세 페이지 링크](https://code.visualstudio.com/docs/customization/userandworkspace#_language-specific-editor-settings)





## 3. 단축키 설정 수정
	파일 > 기본 설정 > 바로가기키
	keybindings.json 수정
	각자 스타일로 셋팅

```json
// 키 바인딩을 이 파일에 넣어서 기본값을 덮어씁니다.
[
	// emmet 실행
	{ "key": "ctrl+e",
		"command": "editor.emmet.action.expandAbbreviation",
		"when": "editorTextFocus && !editorHasMultipleSelections && !editorHasSelection && !editorReadonly && !editorTabMovesFocus" },
	// 계산
	{ "key": "ctrl+shift+y",
		"command": "editor.emmet.action.evaluateMath",
		"when": "editorHasCompletionItemProvider && editorTextFocus && !editorReadonly" },
	// 요소 감싸기
	{ "key": "ctrl+w",
		"command": "editor.emmet.action.wrapWithAbbreviation",
		"when": "editorHasCompletionItemProvider && editorTextFocus && !editorReadonly" },

	// 블럭지정 또는 포커스된 문자 - 소문자로
	{ "key": "ctrl+l ctrl+l",
		"command": "editor.action.transformToLowercase",
		"when": "editorTextFocus" },

	// 블럭지정 또는 포커스된 문자 - 대문자로
	{ "key": "ctrl+l ctrl+k",
		"command": "editor.action.transformToUppercase",
		"when": "editorTextFocus" },

	// 컬러 피커 사용
	{ "key": "alt+c alt+p",
		"command": "extension.colorHelper.pick",
		"when": "editorTextFocus" }
]
```
