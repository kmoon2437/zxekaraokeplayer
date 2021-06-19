# ZXEKaraoke Player
## 개요
ZXE노래방 플레이어이다.
## 요구사항
- node.js 제일 최신. 아 모르겠고 그냥 제에ㅔㅔㅔㅔ일 최신
- midi 모듈을 깔 수 있어야 한다.
- electron을 사용할 수 있어야 한다.
- 경로에는 아스키코드에 있는 문자만 있어야한다(한글같은거 있으면 오류남. 이유는 밑에 나옴).
### tip
- midi 모듈은 경로에 한글이 있으면 설치가 안된다.제작자가 저걸 몰라서 몇날 며칠을 개고생했다.
## 사용법
### 준비
electron과 관련 모듈을 깐다.
- `npm install -g electron@latest electron-rebuild@latest` 를 실행한다.
### 설치/실행
- 적당한 폴더에 download zip을 받은걸 풀어준다.(아니면 git clone해도 좋음)
- `npm install` 명령어를 실행한다. (제작자 컴에서 15분 걸림)
- `electron-rebuild`를 실행한다. (electron에서 실행하기 위해 canvas,midi등의 모듈을 새로 빌드)
  - 만일 안된다면 `npm install nan@2.14.0` 을 실행하고 다시 해보자. (이 부분은 nan 모듈의 버그 때문에 2.14.0으로 새로 깔아야 한다.)
- `electron .`를 실행하면 프로그램이 실행된다.
### 곡 데이터
곡 데이터 생성은 [여기](./manuals/song_data.md)를 참고하세요.

### 추가사항
- midi 반주의 길이는 가장 마지막 note off 이벤트 실행 시간+3초 이다.
- 뮤비가 있는 midi곡의 경우 앞뒤 점프시 뮤비가 같이 점프되지 않는다.
