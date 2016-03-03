## Karma

##### 설치
- Karma는 Node.js 에서 실행되고 NPM 패키지로 사용 가능하다.

1. Node.js 설치
2. 워키 디렉토리에 karma, 관련 플러그인 설치 (node_modules > karma-jasmine, karma-chrome-launcher)
3. 설치 시 명령어는 npm install


##### 환경 설정
- Karma가 잘 실행되기 위해서는 '환경 설정 파일'을 프로젝트 폴더에 생성해야 한다.

1. 명령어 실행
  karma init // 자동으로 설정 파일 생성하며 하단 질문에 맞게 값 설정하면 된다.
  
  Which testing framework do you want to use ? // TC 프레임웍 종류를 묻는다.
  > jasmine
  
  
