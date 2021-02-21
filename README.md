# vue

- Studying Vue.js 

디렉티브는 v- 접두사가 있는 특수 속성 
디렉티브 속성 값은 단일 JavaScript 표현식이 된다.
(나중에 설명할 v-for는 예외입니다.) 디렉티브의 역할은 표현식의 값이 변경될 때 사이드이펙트를 반응적으로 DOM에 적용하는 것이다. 

v-bind : null, undefined 또는false의 값을 가지면 disabled 가 element에 포함되지 않는다.
ex) <button v-bind:disabled="isButtonDisabled">Button</button>

