# CCPPhone

목차

1. BootimeUI
2. BootingOption
3. CCPPosix
4. 마치며
5. 마무리하며

## 1. BootimeUI

1. 키보드 연결이 USB나 Bluetooth로 되도록 BootimeUI-CLI에서 설정이 가능하다. (이것도 config의 힘이다.)
2. BootimeUI-GUI라고, GUI가 설치되지 않았을때, TUI형식의 GUI로, 키보드 앱이 제공된다. 설치 되어있다면 Termux앱에서 Keyboard를 쓰듯이 GUI로 키보드를 쓸수 있다.
3. 이 시스템은 disable가능하다. disable시 USB포트의 키보드를 이용하도록 변경된다.
4. 그리고 볼륨 조절이라던가 하는 등, 은근 안드로이드 흉내는 냈지만, 저작권 침해정도까진 아니다. 그리고 어짜피, half-disable이라고, 전부 disable하지 않고 일부 기능을 이용하거나, 기능들을 커스텀하도록, 지정 어플리케이션에 연결해주는 방식의 유사-disable도 제공해준다.
5. 근데, 에초에, CCPPhone은 설치 후 환경설정 자체를 커스텀 설치가 가능해서 ㅋㅋㅋ 이거 사용도 스킵 가능하다.

## 2. BootingOption

변경할때마다 경고창뜬다. "caution : this option is systemic. it should be use on application or user who amature or pro developer. if this caution is pop up on application, and also you don't want broke your device, it's inevitable to that's application's reliability is enough to controll it. you are solely responsible for this action."라고(저 메세지가 순정 기본 버전이다.). 뭐 근데 시스템 다루거나 코딩할줄 알면 개나소나 amature developer니까 장벽이 아무 의미없긴 한데... 뭐 대충, 저거 실행해서 폰 먹통되었으면, 엄한사람 잡아서, 폰이 이상하다고 시비걸지 말라는 소리임.

BootingOption으로 CCPP실행시 옵션 설정이 가능할 뿐 아니라, CCPP를 제거하거나 편집하는것도 가능하다. 또한, BootingOption중 일부를 설정을 제약걸기 위하여, 비번을 지정하는 작업 역시 BootingOption에서 규정 가능하다.

이게 스마트폰용 OS니까 저런 옵션을 제공하는거다. 통신사 • 디바이스 제조사 • 판매점에 가서, 루팅 기본 OS가 루팅중 고장났다는 nugae merdosae 하는걸 막기 위해서다.

물론, 하드웨어 하자 가지고 SW회사에 오면 ... 답이 없긴 하다. 그래서, BootingOption은 기본적으로, Vanilla Icecream(VIVersion, VIV)이라는 버전이다. VIV은 하자가 있으면 친절히 알려주는거고, Lite Vanilla Icecream은 불친절히 알려주고, Chocolate Icecream은 더 단순하다. 아예 그런 불친절한 기능 대신 거부하고, Lite Icecream은 아예 알려주는 기능도 없다. 에초에 VIV 분류하려고 만든 분류라...

## 3. CCPPosix

1. CcppWebAppLuncher
2. StandardCcppDirectoryFormat
3. CcppModalShellSystem SystemicPipelineVersion ShellSystem & VirtualServerPipelineSystem & CCPPWGUI
4. Posixity
5. CanvasCanProtocal

### 1. CcppWebAppLuncher

1. CCP클라이언트인데, As Config File방식 프록시 설정이고, 굳이 private으로 돌리지 않으면 Public으로써 linux에서 config편집하듯 쓸수 있다. 앱 자체에서 특정 명령을 실행하거나, 설치 옵션에서 그 명령 초기 실행을 설정했다면, 프록시 편집이나 기본값 등을 설정 가능하다.
2. 그리고, StandardCcppDirectoryFormat상에서, 이미 앱 설치시 어떻게 배치할지가 다 정해져있다. 해당 구역를 예약구역이라고 부른다. CCPPosix에서 특정 명령을 실행하거나, CCPPosix설치시에 그 명령 초기 실행을 설정하면, CcppWebAppLuncher가 정해진 위치에 설치된다.
3. CcppModalShellSystem을 실행시, 기존 Shell프로세스가 SSH를 통해가지고 호스팅 이후, GUI의 터미널 창에서 그 호스팅을 받아서 표기하는 DockerLikeVersion이 존재한다. 그러나, 실제론 내부적으로, SystemicPipelineVersion이라고, 내부의 파이프라인으로 실행하는 방식이 Optional로 존재한다. 그것도 이제 내부 명령이 실행시, CcppWebAppLuncher의 유무를 판단하고 설정되는데, 그것 역시 CcppWebAppLuncher설치 초기 실행 여부를 결정 가능하다. 또한, CcppWebAppLuncher설치 이전에, 설치시 그게 실행되게끔 하는 명령도 있는데, 그것도 CCPP내에 명령이 있다.
4. 쉘 설정방법으로 쉘이 지정되는 식이면 되고, 어떻게 지정되었는지는, OS관련 Config정보가 달린곳이 있긴 하다.
5. CcppModalShellSystem SystemicPipelineVersion ShellSystem상태의 Shell인지 판단하는게 OS관련 상수 Config에 존재한다. 그건 이제, 업데이트 가능한 Firmware라서... 기본값은, 5. CcppModalShellSystem SystemicPipelineVersion ShellSystem상태가 아닌거고, CcppModalShellSystem SystemicPipelineVersion ShellSystem은 그냥 CcppWebAppLuncher유무와 무관히 설치 가능하고, OS에서 오프라인에서 설치 가능하다. 다만 lite version으로 OS를 설치했다면, 웹으로 가져온다.
6. `#!CWAL`로 지정되어있는 텍스트 파일은, 거기 적힌 url을 실행시키나, url자체가 proxy서버인 경우, null문자 이후 파일이 ELF인거라, 그걸 실행해서 서버를 연 다음 접속하는 방식이다.
7. VirtualServerPipelineSystem라고, CcppModalShellSystem SystemicPipelineVersion ShellSystem랑 동일 원리로, 걍 서버 환경을, 파이프라인으로 가상화하는거가 있으면 `#!CWAL`실행용이 지정 가능하다.

### 2. StandardCcppDirectoryFormat

뭐 Linux나 Posix의 파일 구조랑 비슷한데, 기본파일 설정이 몇게 있는거다. 이미 어느정도 예상이 될것같으니 생략한다.

### 3. CcppModalShellSystem SystemicPipelineVersion ShellSystem & VirtualServerPipelineSystem & CCPPWGUI

CcppModalShellSystem SystemicPipelineVersion ShellSystem은 이미 너무 많이 설명해서 ㅋㅋㅋㅋ

CcppModalShellSystem SystemicPipelineVersion ShellSystem랑 VirtualServerPipelineSystem원리는 이미 다들 설명되서 알거다.

둘다, Config를 가지고, 뭐어쩌고, 걍 다 똫같다. 빼다 박게 프로그래밍한 시스템이다.

그리고... 대망의 CCPPWGUI는...

CCPPWGUI가 활성화되어있다면, 그것도 OS Firmware에 CCPPWGUI관련 시스템이 설치되어있는거고, 그 경우, CcppWebAppLuncher가 실행 가능하다. 기본적으로 해당 시스템이 설치된다. LiteVersion은 기본적으로 미설치다. (눈치깟겠지만,에초에 Lite는 기본 미설치로 되어있는거 추가설치하면 LiteVersion 아닌 버전이랑 차이가 사실상 없다...)

CCPPWGUI가 있으면, GUI가 있는 OS인 셈이다.

### 4. Posixity

그래도 Posix다. 에초에 걍 CCPPosix는 OS형식인데, 앞서 명시한 설정들이 다 되어있는 Posix를 CCPPosix라 부른다.

뭐... 설명하기에도 너무 뻔하지 않나? 이 시점에서 이미 뻔하게 나오는데.

### 5. CanvasCanProtocal

목차

1. 렌더링
2. 프록시 호스팅
3. 프록시 설정

#### 1. 렌더링

css는 오직 style태그로만 명시되며, canvas를 화면 전체로 정하고, html자체는 css랑 js, wasm만 불러오는, 깡통 HTML/CSS코드를 CanvasCan이라고 부르는 소스코드로, CanvasCanProtocal의 표준에서 고정된 코드(단. HTTP 커스텀 해더의 X-Loader-Script라는 속성에 적힌 URL의 값을 DOM에서 가져와서, LoaderScript로 써먹는 식이다.)로 정해놓고, CanvasCanProtocal 클라이언트 CanvasCanProtocal을 통하여 받은 URL을 다음 두가지중 하나로만 해석해야 한다.

1. CanvasCan가 Body이고, X-Loader-Script가 받은 URL이도록 하는 HTTP해더 "전용" 클라이언트 (즉, 어떻게든, CanvasCan를 미리 DOM에 로드해놔도 되고, HTTP상태도 상수화해도 된다. HTML/CSS를 로드시키기만 하면 된다.)
2. 아예 HTML/CSS시스템 없이, 받은 URL을 걍 바로 처리해버리는 처리기로써 클라이언트가 작동한다.

이 두가지 실행은, 어짜피 LoaderScript 실행 전에 하는 작업이라곤, 실행 준비밖에 없고, LoaderScript실행결과 창에 나타나는 그래픽이, 1번방식이든 2번 방식이든 결과적으로 동일하다.

#### 2. 프록시 호스트

접속하고자 하는 사이트를 CanvasCanProtocal형식에 맞도록 수정한다.

1. 접속하고자 하는 사이트에 Anonymousy라곤 하나도 없는 대놓고 Proxy인 HTTP요청을 보낸다.
2. 받은 결괏값을 토대로, 프록시 서버의 HTTP호스팅상에 해당 URL에 대한 LoaderScript인 JS파일등을 갱신한다.
3. 프록시 고객에게 JS파일 URL을 전송한다. 그 답변이 바로 CanvasCanProtocal이다.

그리고 서버는 세가지 종류가 있다.

1. 캐싱하는 서버 : 기본은 케싱하지 않는 프록시이나, 캐싱해도 된다. 프로토콜의 "허용"사항이다.
2. 유저에게 자원을 이용하는 서버 (정보 저장 • 컴퓨팅 자원 그리딩) : 해당 작업에 "허용"된다. 다만, 어떤 자원을 이용하는지 전문용어로 명시하며, 동시에, 비전문적으로도 이해 가능하게 명시해야한다. 만약, 정상 지능의 성인의 과반이 속게 되는 명시문의 경우, 허용은 무효다.
3. 가상서버 : 서버가 존재하지 않는데, 그걸 제공하는 망 자체에서, 가상의 IP에 서버를 지정하고, 실제론 서버가 없는데, IP랑 통신하면, 어쨌든 서버처럼 작동해도 된다. 이건 Server on VPN이라 부른다(다만 그 망이 VPN일 필요는 없다. 그냥 상품명처럼 이름을 지은거다.). 이걸 극단적으로 줄이면, 그 망에 접속자가 1개인 방식으로 제공해도 된다. 이는 Client-Server가 한 구역에 존재하는것이라, Server As Me라고 부른다.

#### 3. 프록시 설정

1. Before Open App
2. After Open App
3. As Config File (Public • Private) 

BOA : 앱을 열기 전에 설정하는거다.
AOA : 앱을 연 후에 설정하는거다.
ACF : 그냥 Config파일에 설정하는식으로 해서, 앱이, BOA든 AOA든, 클라이언트 • 프록시 설정앱 개발자가 알아서 결정하도록 한다. 다만, 보안을 위해 Private에 저장하는걸 "허용"한다. Public에 저장하는걸 "기본"으로 한다.

## 4. 마치며

이걸 통해 참운영체제다운(재대로 된(=커스텀 가능한) 운영체제다운) CLI + WUI스마트폰을 사용할수 있다.

그리고 그런 폰을 원하는 사람은 존재한다. 그 존재성은 내가 존재하는 한 이미 구성적 증명(대상을 제시하는 수학적 구성주의철학적 증명)이 되어있음이 자명하다

## 5. 마무리하며

커스텀 가능한 폰 가지고싶어 커스텀 가능한 폰 가지고싶어 커스텀 가능한 폰 가지고싶어 커스텀 가능한 폰 가지고싶어 커스텀 가능한 폰 가지고싶어 커스텀 가능한 폰 가지고싶어 커스텀 가능한 폰 가지고싶어 커스텀 가능한 폰 가지고싶어 커스텀 가능한 폰 가지고싶어 커스텀 가능한 폰 가지고싶어 커스텀 가능한 폰 가지고싶어 커스텀 가능한 폰 가지고싶어 커스텀 가능한 폰 가지고싶어 커스텀 가능한 폰 가지고싶어 커스텀 가능한 폰 가지고싶어 커스텀 가능한 폰 가지고싶어 커스텀 가능한 폰 가지고싶어 ㄹㅇ