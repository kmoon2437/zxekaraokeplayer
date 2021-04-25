# ZXEKaraoke Player
## 개요
ZXE노래방 플레이어이다.
## 요구사항
- midi,electron,canvas 모듈을 깔 수 있어야 한다.
- 경로에는 아스키코드에 있는 문자만 있어야한다(한글같은거 있으면 오류남).
### tip
- midi 모듈은 경로에 한글이 있으면 설치가 안된다.
- canvas 모듈은 그냥 node에서 쓸땐 바로 컴파일이 되는데(윈도우 기준), electron에서 쓰려면 gtk라는 라이브러리를 다운받아서 `C:/GTK`에 풀어야 한다.(밑에 나옴)
- 제작자가 위 2개를 몰라서 몇날 며칠을 개고생했다.
## 사용법
### 준비
canvas 모듈의 의존성 라이브러리를 깐다.
- 윈도우 환경
  - gtk를 다운받는다. [32비트](http://ftp.gnome.org/pub/GNOME/binaries/win32/gtk+/2.24/gtk+-bundle_2.24.10-20120208_win32.zip) [64비트](http://ftp.gnome.org/pub/GNOME/binaries/win64/gtk+/2.22/gtk+-bundle_2.22.1-20101229_win64.zip)
  - 압축파일 안에 있는걸 `C:/GTK` 에다가 풀어준다.
- 맥os 환경
  - `brew install pkg-config cairo pango libpng jpeg giflib librsvg` 를 실행한다.([homebrew](https://brew.sh) 사용)
- 리눅스/기타 유닉스 환경
  - os에 따라 아래 명령어를 실행한다.
    - 우분투: `sudo apt-get install build-essential libcairo2-dev libpango1.0-dev libjpeg-dev libgif-dev librsvg2-dev`
    - 페도라: `sudo yum install gcc-c++ cairo-devel pango-devel libjpeg-turbo-devel giflib-devel`
    - Solaris: `pkgin install cairo pango pkg-config xproto renderproto kbproto xextproto`
    - OpenBSD: `doas pkg_add cairo pango png jpeg giflib`
### 설치/실행
- 적당한 폴더에 download zip을 받은걸 풀어준다.(아니면 git clone해도 좋음)
- `npm install` 명령어를 실행한다. (제작자 컴에서 15분 걸림)
- `electron-rebuild`를 실행한다. (electron에서 실행하기 위해 canvas,midi등의 모듈을 새로 빌드)
  - 만일 안된다면 `npm install nan@2.14.0` 을 실행하고 다시 해보자. (이 부분은 nan 모듈의 버그 때문에 2.14.0으로 새로 깔아야 한다.)
- `electron .`를 실행하면 프로그램이 실행된다.
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
