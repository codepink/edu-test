## Charles

#### 개요
- 웹 개발 시 **웹 디버깅 툴**이 필요하다.
- IE, 크롬, 사파리 등 웹 브라우저 내에도 디버깅 툴이 내장되어 있으며, 대표적인 프록시 도구로는 **Fiddler**가 있다.
- Fiddler는 클라이언트 - 서버 사이의 요청(Request)과 응답(Response)에 대한 모든 데이터를 확인할 수 있다.
- 안타깝게도(?) Mac용 Fiddler는 제공하지 않으며, 이를 대체할 어플리케이션으로 **Charles**가 사용된다.
- 참조 : [Mac을 위한 프록시 도구 모음](http://formac.informer.com/fiddler)
  
  
#### 설치
1. <https://www.charlesproxy.com/download/> 에서 OS에 맞는 최신 버전의 설치 파일을 다운로드 한다. (Mac OS X 환경은 dmg 파일 다운로드, 유료 라이센트 구매 필요)
2. 다운로드한 dmg 파일을 실행하여 설치 진행  
![ScreenShot](/screenshot/charles01.png)
3. 통신 캡쳐링을 위한 세팅 : 실행 후 [Proxy] > [Mac OS X Proxy] 메뉴가 활성화 되어있는지 확인한다. (비활성화된 경우 체크)  
![ScreenShot](/screenshot/charles02.png)
  
  
#### 맛보기
![ScreenShot](/screenshot/charles03.png)
- 세션 보기 모드 설명
  * Structure : 트리 형태로 요청 내역을 보여준다. (디폴트 모드)
  * Sequence : 시간 순(요청이 들어오는 순서)으로 요청 내역을 보여준다.
- 기본 탭 설명
  * Overview : 요청 & 응답에 대한 내역을 간략하게 볼 수 있다.
  * Request : 요청 정보(헤더, 쿼리스트링, 쿠키 등)를 확인할 수 있다.
  * Response : 응답 데이터를 확인할 수 있다.
  * Summary : 각 리소스별로 응답 내역을 확인하고 비교하는 용도로 사용된다.
  * Chart : 요청(dark blue 막대 표시)부터 응답(light blue 막대 표시)까지 결과를 타임라인 차트로 보여준다.
  
  
#### 툴 활용하기 (테스트 예제)
![ScreenShot](/screenshot/charles04.png)  
- **Map Remote Tool** : 서버로부터 리소스 파일의 요청지를 변경할 수 있다.
- **Map Local Tool** : 원격 서버의 파일을 로컬 파일로 대체할 수 있다. 수정된 파일을 서버에 업로드 하지 않아도 로컬에서 바로 확인할 수 있어 테스트 환경에서 유리하다.

##### [테스트 1] 다른 서버의 이미지로 변경하기 (Map Remote Settings 설정)
1. [Tools] > [Map Remote] 메뉴 클릭하여 현재 응답 리소스와 변경할 리소스의 요청지 정보를 입력한다.   
![ScreenShot](/screenshot/charles05.png)  
2. 브라우저 캐시 삭제 후 페이지를 재 요청하면 이미지가 변경된다. (응답 body 내 이미지 URL은 변경되지 않는다)  
[origin]  
![ScreenShot](/screenshot/charles06.png)  
[modify]  
![ScreenShot](/screenshot/charles07.png)

##### [테스트 2] alert 실행 코드를 추가한 로컬 파일로 변경하여 스크립트 실행 (Map Local Settings 설정)
1. 세션에서 변경하고자 하는 파일을 검색하여 로컬에 저장 후 에디터로 편집한다.
2. [Tools] > [Map Local] 메뉴 클릭하여 원격지 응답 파일의 정보를 입력하고 1번에서 편집한 로컬 파일을 변경 파일로 등록한다.
![ScreenShot](/screenshot/charles08.png)  
![ScreenShot](/screenshot/charles09.png)  
3. 브라우저 캐시 삭제후 페이지를 재 요청하면 로컬 파일로 대체되고 추가된 스크립트가 실행된다.
![ScreenShot](/screenshot/charles10.png)
