## Jasmine & Karama


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
- toBe() / not.toBe()
- toBeTruthy() / toBeFalsy()
- toContain() / not.toContain()
- toBeDefined() / toBeUndefined()
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

##### Jasmine & Karma 테스트
1. bower로 프로젝트 구성
    - bower는 npm, gem 같은 FE 패키지 매니저다.
    - <http://bower.io/search/>에서 필요로 하는 패키지를 검색해서 설치할 수 있다.
    - 예제에서는 <https://github.com/sjswoboda/karma-jasmine-runner2-reporter> 패키지 설치
2. Karma 초기화
    - karam.conf.js 파일 생성이 필요하며 **karma init** 명령어로 생성한다.  
    ![ScreenShot](/screenshot/day2_01.png)  
3. Karma 연동
    - 테스트를 위한 자바스크립트 라이브러리를 로드해야 한다.
    - 2번에 해당하는 파일을 수정한다. (**files** 설정값에 해당) 
    ![ScreenShot](/screenshot/day2_02.png)
4. Karma 정상 실행 확인
    - 프로젝트 루트에서 **karma start** 명령어를 실행한다.
    - 커맨드 라인으로 상태 확인 가능  
    ![ScreenShot](/screenshot/day2_03.png)  
5. Jasmine으로 테스트 코드 작성 및 실행
