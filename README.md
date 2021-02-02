# ZXE Karaoke player
노래방 플레이어이다.
# 요구사항
es6 이상
video 태그 autoplay
... 아 모르겠고 걍 크롬(chrome) 쓰자
# 사용법
웹서버나 웹호스팅 등이 있다면:
1. 웹루트에 아무데나 폴더를 2개 만든다.(저장소 폴더,플레이어 폴더. 가상호스트 2개여도 좋다)
2. download zip을 사용해 압축파일을 받아 플레이어 폴더에 풀어준다.
   (git clone을 사용해도 된다)
3. js/config.js 파일을 열어 아래 내용을 입력한다.
```js
var cfg = {
    archive_url:"http(s)://(웹서버 주소)/(저장소 경로)"
};
```
4. 브라우저로 http://(웹서버 주소)/(플레이어 경로)에 접속한다. 팝업창이 하나 열릴 것인데, 저장소 설정 로드 중에서 멈춰도 괜찮다.

없거나 귀찮다면:
1. 아무데나 폴더를 2개 만든다.(저장소 폴더,플레이어 폴더)
2. download zip을 사용해 압축파일을 받아 플레이어 폴더에 풀어준다.
   (git clone을 사용해도 된다)
3. js/config.js 파일을 열어 아래와 같이 수정한다.
```js
var cfg = {
    archive_url:"(저장소 폴더의 상대 경로)"
};
```
4. 브라우저로 index.html 파일을 연다. 팝업창이 열릴 것인데, 저장소 설정 로드 중에서 멈춰도 괜찮다.

공통:
5. 저장소 폴더에 kar_db.json과 archive.json 파일을 만든다.
6. archive.json 파일을 열어 아래 내용을 입력한다.
```json
{
    "dbfile_name":"kar_db.json",
    "songs_dirname":"songs"
}
```
7. kar_db.json 파일을 열어 아래 내용을 입력한다.
```json
{
    "원하는 숫자(최대 5자리). 노래방 번호가 될거임":{
        "title":"제목",
        "subtitle":"부제목. 없다면 이 줄은 없어도 됨",
        "key":["성별. M은 남자,F는 여자,X는 혼성키다","키"],
        "info":{
            "song":"가수",
            "lyrics":"작사자",
            "music":"작곡자",
            "origin":"원곡. 없다면 이 줄은 없어도 됨"
        }
    }
}
```
8. 저장소폴더에 songs 폴더를 만들고, songs 폴더에 아까 넣었던 숫자를 넣는다.
9. http://choyunjin.kr/page/kar_manual?name=lyrics 을(를) 참고하여 lyrics.zkr과 mr 등을 넣는다.
10. 아까 그 팝업창을 새로고침한다.
11. 곡번호 칸에 아까 그 숫자를 키패드로 입력한 뒤(input은 따로 없고 걍 입력하면 입력이 된다.) enter를 누르면 팝업창에 노래가 틀어진다.
12. esc키로 노래를 끌수 있고, 스페이스바로 곡을 일시정지할 수 있다.
