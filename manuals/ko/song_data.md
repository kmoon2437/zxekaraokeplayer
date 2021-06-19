# 곡 데이터 구성
## 폴더 구조
### 현재 컴퓨터에 곡을 저장하는 경우
```
저장소로 지정된 폴더
┗ 1 // 폴더명은 숫자여야 하며, 곡번호로 사용. 최대 5자리까지 가능
  ┗ data.zxe
  ┗ 반주파일.ogg // vorbis 권장
  ┗ 뮤비.mp4 // h264+aac 권장. 반주까지 여기에 넣었으면 반주파일은 따로 없어도 됨
  ┗ 미디파일.mid // midi format 1 권장. 미디파일이 있으면 다른 반주파일 무시
┗ 2
  ┗ ...
┗ 3
  ┗ ...
```
### 서버에 곡을 저장하는 경우
```
웹 루트 또는 그 밑의 저장소용 폴더
┗ archive.json // 저장소 설정파일. 이하는 아래 참고
┗ kar_db.json // 저장소 설정파일에서 원하는 파일명으로 변경 가능
┗ songs // 저장소 설정에서 원하는 폴더명으로 변경 가능
  ┗ 1 // 폴더명은 숫자여야 하며, 곡번호로 사용. 최대 5자리까지 가능
    ┗ data.zxe
    ┗ 반주파일.ogg // vorbis 권장
    ┗ 뮤비.mp4 // h264+aac 권장. 반주까지 여기에 넣었으면 반주파일은 따로 없어도 됨
    ┗ 미디파일.mid // midi format 1 권장. 미디파일이 있으면 다른 반주파일 무시
  ┗ 2
    ┗ ...
  ┗ 3
    ┗ ...
```
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
