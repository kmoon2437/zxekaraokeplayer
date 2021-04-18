# ZXEKaraoke Player
## 개요
ZXE노래방 플레이어이다.
## 요구사항
- midi,electron,canvas 모듈을 깔 수 있어야 한다.
- 경로에는 아스키코드에 있는 문자만 있어야한다(한글같은거 있으면 오류남).
### tip
- midi 모듈은 경로에 한글이 있으면 설치가 안된다.
- canvas 모듈은 그냥 node에서 쓸땐 바로 컴파일이 되는데(윈도우 기준), electron에서 쓰려면 gtk라는 라이브러리를 다운받아서 c:/GTK에 풀어야 한다.
- 제작자가 위 2개 때문에 몇주를 개고생했다.
## 사용법
1. 적당한 폴더에 download zip을 받은걸 풀어준다.(아니면 git clone해도 좋음)
2. `npm install` 명령어를 실행한다. (제작자 환경기준 15분 걸림. 버그인듯)
3. `npm install nan@2.14.0` 을 실행한다.
> nan 2.14.1~의 버그 때문에 2.14.0으로 새로 깔아야 한다.
4. `electron-rebuild`를 실행한다.
5. `electron .`를 실행하면 프로그램이 실행된다.
### 키(음정)
- 숫자로 기록된다.
- Minor(단조) 인 경우 음수로 하면 된다.
<table>
    <th><td>번호</td></th>
    <tr><td>C</td><td>1</td></tr>
    <tr><td>C#</td><td>2</td></tr>
    <tr><td>Db</td><td>3</td></tr>
    <tr><td>D</td><td>4</td></tr>
    <tr><td>D#</td><td>5</td></tr>
    <tr><td>Eb</td><td>6</td></tr>
    <tr><td>E</td><td>7</td></tr>
    <tr><td>F</td><td>8</td></tr>
    <tr><td>F#</td><td>9</td></tr>
    <tr><td>Gb</td><td>10</td></tr>
    <tr><td>G</td><td>11</td></tr>
    <tr><td>G#</td><td>12</td></tr>
    <tr><td>Ab</td><td>13</td></tr>
    <tr><td>A</td><td>14</td></tr>
    <tr><td>A#</td><td>15</td></tr>
    <tr><td>Bb</td><td>16</td></tr>
    <tr><td>B</td><td>17</td></tr>
</table>

### 추가사항
- midi 반주의 길이는 가장 마지막 note off 이벤트 실행 시간+5초 이다.
- 뮤비가 있을 경우 midi 반주의 길이는 뮤비보다 길면 안된다. 왜냐하면 뮤비가 없을땐 Date.now()를 사용하지만 뮤비가 있으면 뮤비의 currentTime 을 사용하기 때문이다.
