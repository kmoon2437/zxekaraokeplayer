# ZXEKaraoke Player
## 개요
ZXE노래방 플레이어이다.
## 요구사항
- midi,electron,canvas 모듈을 깔 수 있어야 함
### tip
- midi 모듈은 경로에 한글이 있으면 설치 안됨(제작자가 이걸로 몇날 며칠을 개고생했음)
## 사용법
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
- midi 반주의 길이는 가장 마지막 이벤트 실행 시점+5초 이다.
- 뮤비가 있을 경우 midi 반주의 길이는 뮤비보다 길면 안된다. 왜냐하면 뮤비가 없을땐 Date.now()를 사용하지만 뮤비가 있으면 뮤비의 currentTime 을 사용하기 때문이다.
