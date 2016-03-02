### Jasmine & Karama


##### Jasmine
- 자바스크립트용 유닛 테스트 프레임워크(Unit Test Framework)의 한 종류이다.
- 유사 프레임워크로는 QUnit, mocha.js, Sinon 등이 있다. (<http://stackoverflow.com/questions/300855/javascript-unit-test-tools-for-tdd>)
- BDD 기반 (<https://en.wikipedia.org/wiki/Behavior-driven_development>)

##### Jasmine 주요 용어
- Suite
    - 무엇을 테스트 하는지 용도를 설명하기 위함
    - describe() 함수에 해당
    - 1개의 Suite 안에는 여러 개의 Spec이 존재할 수 있다.
- Spec
    - 무엇을 테스트 할지에 대한 명세(Specification)
    - it() 함수에 해당
- Macher
    - 어떤 Suite로 코드를 테스트 했을 때 정상적인 결과값(true)을 반영하는지 체크하는 것
    - Jasmine API에 해당
    - **내장 매쳐(API)** 외 **유저 생성 매처**를 생성할 수 있다.

##### Jasmine 주요 API
- toEqual()
- toBe(), not.toBe()
- toBeTruthy(), toBeFalsy()
- toContain(), not.toContain()
- toBeDefined(), toBeUndefined()
- toBeNull()
- toBeNaN()
- toBeGreaterThan()
- toBeLessThan()
- toBeCloseTo()
- toMatch()
- toThrow()
- spyOn()

##### Jasmine 비동기 테스트
1. 다음 2개 API를 사용하여 테스트
    - runs() : 비동기 테스트 함수 호출 시 순차적으로 다음 코드를 실행시켜 줄 때 사용한다.
    - waitsFor() : 함수 호출시 결과 값이 true 일 때만 다음 코드를 실행할 수 있다. (타임아웃 발생 가능)
2. **jasmine-ajax 플러그인(<http://jasmine.github.io/2.0/ajax.html>)** 사용하여 테스트

##### Karma
- 테스트 러너(Test Runner)라고 부른다.
- 유닛 테스트 프레임워크와는 다르다. (= 유닛 테스트 코드를 실행하는 도구라고 보면 된다)
- 터미널 환경에서 유닛 테스트 실행을 확인할 수 있다.

##### Karma 설치하기
1. Node.js 상에서 npm 패키지로 설치 가능하다.
2. <https://nodejs.org/en/download/> 에서 Node.js 설치한다.
3. Node.js 설치 완료하면 다음 명령어로 karma 설치를 진행한다.
    $npm install -g karama
4. karma가 정상적으로 설치되었는지 확인한다.
    $karma --version
    Karma version: 0. 13.2
