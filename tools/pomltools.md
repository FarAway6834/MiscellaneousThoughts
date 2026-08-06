# pomltools

목차
1. poml
2. pomldocs
3. pomltextfiletree

## Pydgin-OML(Python Tom'sObiousMinimalLangugage Pidgin)

다음과 같은 poml file
```
[!poml.begin("section")]
[section]
⋯
[!poml.end("section")]
```
은

```
import pydginoml

[!poml.begin("section")]
[section]
⋯
[!poml.end("section")]
```
로 컴파일되며

Python Bytecode, magic-method, builtins, cython, C를 통하여 저 과정이 동작 가능하도록 한다.

특이사항 : 
1. poml.begin이 시작된 동안엔, 다른 poml.begin은 불가능하다.
2. poml.end를 통하여, poml.__import__("moudle").section을 등록 가능하다. 그 이전까진, 해당 사항은 등록되지 않는다.
3. poml.__import__("moudle")은 해당 module이 import되지 않았을 경우, forse라는 kw-only argument값에 따라서, import될수도, 아닐수도 있다.
4. poml.begin(as = section.⋯)을 하게 되면, poml.__import__를 통하여 begin도중에 불러와진 섹션을 section.⋯에다가 추가하도록 할수 있으며, 이는 poml.end로 해제 가능하다. 이때, poml.begin의 kw-only argument인 as를 제외한 다른 argument(즉, pos-only argument)가 None이 아니라면, 그 의미를, 해당 None은 특정 섹션 할당용으로 사용되었다는 의미가 된다.
5. __enter__로 begin을 쓸수 있다. __exit__로 end를 쓸 수 있다. end이 as속성은, begin에서 as를 받지 않은 경우에만 작동한다.
6. poml.__export__("module").section을 쓰면, 섹션을 pop하여, 다른 색션을 위해서 할당하거나, 혹은 독립시키는 용도로 사용 가능하다.
7. poml.compile을 이용하면, poml코드를 python코드로 컴파일 가능하다.옵션에, inputfile, outputfile설정 가능하며, 기본은 None이다.
8. poml.compile에서, inputfile이 python파일이고, outputfile이 toml이면, python객체를 toml로 변환하되, byte_as_b64옵션이 꺼져있다면, dump불가한건 toml불가한 파일이라며 애러네고, byte_as_b64옵션이 켜져있다면, 문자열 덤프는 "t⋯", 바이트 덤프는 "b⋯"로 처리된다.
9. poml.compile에서 toml을 poml로 바꾸려면, discompile_option이라는 인자이 poml.DiscompileOptionType를 설정해서 줘야함.
10. poml.compile에서, root_as_pyz라는 옵션에서는, None이 아니라, 유효한 pyz경로가 있다면, pyz내의 파일을 와일드카드 등으로 지정하거나 하여, 경로에서 바꾸고자 하는 놈을 지정 가능하다.

## pomldocs : poml을 이용한 python docs system

pomldocs.__config__.__cp__ : 복사시킴 (이쪽으로 가져오든, pyz든 dir이든 아주 잘 함)
pomldocs.__config__.__rm__ : 제거시킴 (이쪽으로 가져오든, pyz든 dir이든 아주 잘 함)
pomldocs.__fix__ : __config__랑 다르게, 그냥 이 파일 자체를 수정한다는 차이밖에 없음. 컴파일러에 의해 감지되야 하므로, 예기치 않게 실행되면 에러를 출력함.
pomldocs에서 havy, lite옵션 : havy는 poml을 참조하고, lite는 poml을 참조하지 않음. 물론 poml자체가 미설치시, opt라는 kw는 None이 아닐수 없음.

cython용으로도 용이하게 쓸수 있을것으로 전망함.

pomldocs.__virtual__로, 가상접근도 지원함.
잡것들은 pomldocs.__nonvirtual__내에 존재함.

그러나... pomldocs는 사실, poml로 작성되었음. 즉, from pomldocs import pomldocs는 일게 색션을 편하게 불러와주는 장치에 불과함. 왜냐? poml begin-end가 아닌 위치는 toml에 집계 인되고, 동시에 선언된 변수를 poml객체에 이전시키지도 않는데, 이 부분을 모듈처럼 응용한거임.

pomlproj를 통하여, 프로젝트 조율등이 가능하고, pomlpypi를 통하여, 배포용 옵션도 가능. 그중에는, FINISH_OFF라는 명령•옵션•개념이 있는데, 아예 문서를 제거하는 옵션이다. pomlorch옵션은, orchestra라 해서, pomldocs의 여러 기능들을 조율해주는 역할임.

아예 웹으로 이전시키는 기능도 존재하는데, pomlwget • pomlcurl • pomlgits • pomlpips, pomlhttp • ... 등 다양하다.

그리고, 아예 웹에서 긁어오듯이, 이 포멧에서 벗어나는 애들 지원용도 있는데, pomlwebs랑 pomlsite다. pomlsite는 정직히 긁고, 동적인 목적이 없다. 반면에, pomlwebs는 동적으로, 검색엔진처럼 쓸 수 있다. pomlsite가, 어떤 페이지를 불러오는 지정으로, 사실상, 지정 매핑 함수만 있다면, 기존 포멧과 동형으로 변환 가능한데 비해, pomlwebs는 전혀 그렇지 않다.

pomlfile은, pomlsite마냥 file중에 그럴수 있고, pomlstor은, 웹 스토리지 접속법을 언제든지 설정 가능하니, pomlfile가 언젠 file이었다, 언젠 usb였다, 언젠 web storage일수 있다.

그리고, pomlable은 pomlproj여부를 enable/disable제어해준다.

이는, pomldocsindev와, pomldocs가 궁극적으로 같은 프로젝트로 관리하도록 해준다.

pomldocsindev를 pomldocsindev나 pomldocs에 의존하지 않게 만드는 용도다.

pomldocsindev는 그냥 poml로만 빌드한거고, pomldocs는 poml과 pomldocs류를 쓰니까.

pomldocslite를 통하여, 아예 경량화된 버전도 사용 가능한 업데이트가 예정되어있다. 빌드 옵션가지고 존나 하드하게 뭔가를 해서 만들어질 예정.

## pomltextfiletree

poml을 filetree용도로 사용한다. pomlfiletree에서 접속법을 주거나, 아니면, 파일시스템 내 아카이브처럼 쓰거나 하므로, 디스크마냥 취급할수도, 아카이브처럼 취급할수도 있다.

pomlfiletreeplus를 통하여, 추가적인 기능을 사용할수 있다. 뭐...

링크라던가, 바이너리라던가...

뭐, 이런걸 만들고 싶은 개발자의 욕망이 있었다.

pomltreeprojorch로, 어떤 file tree를 proj로 쓴다면, 그러한 환경을 할지 안할지 환경화/비환경화하거나, pomldocs와 연동하는 기능도 제공한다. pomldocsindev에 의존한다만, pomldocs도 여기에 의존하게 될듯.

빌드 의존성을 보자면,
poml -> pomldocsindev -> pomltextfiletree -> pomldocs
순인거다.