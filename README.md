# Discord 콘솔 해킹
[![라이선스: GPL v3+](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

:warning: **참고:** 저는 Discord와 관련이 없으며 이러한 스크립트를 사용하는 것을 권장하지 않습니다. 여기에 있는 모든 것을 자신의 책임하에 사용하십시오. 이는 **교육 목적으로만** 사용되며 이러한 코드 블록을 사용하면 계정이 비활성화/해지될 수 있습니다.

## 지역 사회

<details>
<summary>Matrix에 참여하세요!</summary>
  
Matrix는 Discord와 달리 사용자 지정 클라이언트 및 수정을 촉진하는 커뮤니티 기반의 분산형, 개인 정보 보호, 엔드 투 엔드 암호화(슈퍼 보안), 무검열 및 오픈 소스 메시징 프로토콜입니다. 사용 가능한 여러 클라이언트가 있으며 가장 인기 있는 클라이언트(및 참조 구현)는 Element입니다. 대부분의 운영 체제에서 실행되며 꽤 좋은 웹 버전도 있습니다. 자세한 내용은 https://matrix.org 및 https://element.io를 확인하세요.<br>
저는 종종 다음과 같은 질문을 받습니다. "*Matrix가 정말 훌륭하다면 왜 더 일찍 사용하지 않았나요?*"<br>
사실 저는 꽤 오랫동안 Matrix를 사용해 왔습니다. 이 Discord 작업에 사용할 생각은 없었습니다.
</details>

커뮤니티 초대: https://matrix.to/#/#discord-oxygen:matrix.org

주요 커뮤니티는 Matrix에 있으며 대부분의 채널은 암호화되어 있으며 Matrix 내에서만 액세스할 수 있습니다.
Matrix를 사용할 수 없는 분들을 위해 Discord 서버를 만들었습니다. 커뮤니티와 연결되어 있습니다. (Discord에서 보내는 모든 메시지는 자동으로 Matrix에 나타나며 그 반대도 마찬가지입니다.)<br>
초대 링크: https://discord.gg/m8jbrkzExz (4차 서버)<br>


내가 보내지 않은 콘솔 해킹을 사용하지 마세요. 그렇지 않으면 계정을 잃을 위험이 있습니다.<br>
예를 들어 내 계정이 손상되거나 Discord가 서버를 종료하는 경우 이 초대를 정기적으로 업데이트하겠습니다. 그런 일이 발생하면 새 계정, 새 서버를 만든 다음 위의 초대를 업데이트하겠습니다.<br>
초대가 더 이상 작동하지 않으면 서버가 삭제된 것이므로 새 계정을 만들 수 있을 때까지 기다려야 합니다.

## Discord의 내부 작동 방식

**면책 조항:** 이 섹션에서 제공되는 정보는 리버스 엔지니어링을 통해 얻은 것이며 정확성이 검증되지 않았습니다. 따라서 구식일 수도 있습니다.

<details>
<summary>확장</summary>

<br>

### Discord 토큰 구문

<details>
<summary>확장</summary>

<table>
  <tr><th></th><th>예제</th></tr>
  <tr><td>Base64로 인코딩된 사용자 ID</td><td>NTzQvPcLBacBmgajXQc7QAaU</td></tr>
  <tr><td>도트</td><td>.</td></tr>
  <tr><td>base64로 변환된 타임스탬프 -epoch(1293840000)</td><td>XCgboz</td></tr>
  <tr><td>도트</td><td>.</td></tr>
  <tr><td>27자로 구성된 HMAC(대문자/소문자, 숫자 또는 _)</td><td>c4t51kFWSEmdmaPnKoyUuu8E78E</td></tr>
</table>
정확한 토큰 구조를 보여주는 <a href="https://github.com/hxr404/Discord-Console-hacks/issues/2">#2</a>의 멋진 다이어그램이 있습니다.<br><br >
<img src="https://user-images.githubusercontent.com/34555296/120932740-4ca47480-c6f7-11eb-9270-6fb3fbbd856c.png"></img> <br>
</details>
<br>


### Discord의 내부 서버 구조

<details>
<summary>확장</summary>

리버스 엔지니어링 Discord에 대한 이 기사와 Discord가 암호화된 데이터를 해독한다는 증거를 확인하십시오. <a href="https://medium.com/tenable-techblog/lets-reverse-engineer-discord-1976773f4626">https:/ /medium.com/tenable-techblog/lets-reverse-engineer-discord-1976773f4626</a><br>
그들은 또한 귀하의 메시지(예: DM)를 읽고, 모든 편집 및 삭제된 메시지를 기록하고 음성 통화를 녹음할 수 있습니다.

![그래픽](https://user-images.githubusercontent.com/55095883/116671170-e9f5e580-a9a0-11eb-98f9-3bcd65b9fdbf.png)

<br>
<sup>Discord에서 오디오/비디오 메시지 전송 방식</sup>
</details>
<br>
</details>
<br>


## 콘솔 해킹

면책 조항에 명시된 바와 같이 저는 어떤 종류의 클라이언트 수정 사용도 홍보하지 않습니다. 여기에 있는 코드를 불법/해킹 목적으로 사용하지 마십시오. 그렇지 않으면 다음 오류 메시지가 표시될 수 있습니다.

![이미지](https://user-images.githubusercontent.com/55095883/134189043-4da003de-4829-4d60-888a-6014ebb5c2b8.png)

<details>
<summary>확장</summary>

## 이 해킹을 사용하는 방법

웹 및 데스크톱 버전(Windows, Linux, MacOS)에서만 작동하며 모바일에서는 작동하지 않습니다.
1. CTRL + SHIFT + I를 눌러 개발자 도구를 전환합니다(Discord는 기본적으로 Google Chrome인 Electron을 기반으로 합니다).
2. 아직 선택하지 않은 경우 "콘솔"을 클릭합니다.
3. 명령 필드에 스크립트 붙여넣기
4. 엔터를 누르세요

<br>


### 토큰 받기

토큰을 클립보드에 복사합니다.<br>
**:경고: 아무에게도 주지 마십시오. 계정에 대한 전체 액세스 권한을 부여합니다.**

<details>
<summary>확장</summary>

다음을 콘솔에 붙여넣습니다(로그인된 상태에서).

```js
window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x) ].exports).filter((x) => x)) {if (m.default && m.default.getToken !== 정의되지 않음) {return copy(m.default.getToken())}if (m.getToken !== 정의되지 않음) {return copy(m.getToken())}}}]); console.log("%c작동했습니다!", "글꼴 크기: 50px"); console.log(`%c이제 클립보드에 토큰이 있습니다!`, "글꼴 크기: 16px")
```

이제 토큰이 클립보드에 있어야 합니다.<br>
토큰을 붙여넣을 때 다른 사람에게 보내는 것은 주소, 키, 여권/신분증을 제공하는 것과 같으니 주의하세요.<br>
당신의 토큰을 아는 누군가가 당신을 사칭하고, 당신의 친구와 서버를 건드리고, 당신의 돈을 쓸 수 있고(니트로에 지불 방법을 추가한 경우), 심지어 당신의 IP 주소(아마도 당신의 실제 집 주소)를 새로운 장치 기능.

</details>
<br>


### 토큰을 사용하여 로그인

토큰을 사용하여 로그인할 수 있도록 로그인 화면을 수정합니다.

<details>
<summary>확장</summary>

로그인 화면의 콘솔(CTRL + SHIFT + I)에 붙여넣기(로그아웃해야 함):

```js
함수 로그인(e) {setInterval(() => {window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c)) .map((x) => req.c[x].exports).filter((x) => x)) {if (m.default && m.default.setToken !== 정의되지 않음) {return m.default .setToken(e)}if (m.setToken !== 정의되지 않음) {return m.setToken(e)}}}]);console.log("%cWorked!", "글꼴 크기: 50px");} , 50), setTimeout(() => {window.location.reload()}, 2500)}function buttonlogin(){login(document.getElementsByClassName("inputDefault-3FGxgL input-2g-os5")[0].value )}var 요소;(요소=document.getElementsByClassName("marginBottom8-emkd0_ button-1cRKG6 button-f2h6uQ lookFilled-yCfaCM colorBrand-I6CyqQ sizeLarge-3mScP9 fullWidth-fJIsjq grow-2sR_-F")[0]).addEventListener("클릭 ",buttonlogin),(요소=문서.getElementsByClassName("marginBottom20-315RVT")[0]).parentElement.removeChild(element),(element=document.getElementsByClassName("colorStandard-21JIj7 size14-3fJ-ot h5-2RwDNl title-3hptVQ defaultMarginh5-3Jxf6f")[0] ).innerHTML="토큰",element.id="토큰",(요소=document.getElementsByClassName("transitionGroup-bPT0qU qrLogin-1ejtpI")[0]).parentElement.removeChild(요소),(요소=document.getElementsByClassName ("verticalSeparator-2r9gHa")[0]).parentElement.removeChild(요소);getElementsByClassName("transitionGroup-bPT0qU qrLogin-1ejtpI")[0]).parentElement.removeChild(element),(element=document.getElementsByClassName("verticalSeparator-2r9gHa")[0]).parentElement.removeChild(element);getElementsByClassName("transitionGroup-bPT0qU qrLogin-1ejtpI")[0]).parentElement.removeChild(element),(element=document.getElementsByClassName("verticalSeparator-2r9gHa")[0]).parentElement.removeChild(element);
```

이제 토큰을 사용하여 로그인할 수 있습니다.<br>
봇 토큰에서는 작동하지 않습니다. 봇 토큰은 사용자 토큰과 다르며 Discord는 이를 지원하지 않습니다.<br>

![예제 이미지](https://user-images.githubusercontent.com/55095883/105732516-d0bc4380-5f30-11eb-959f-9fae0ddc9b7b.png)<br>
<sup>해킹 실행 후 로그인 화면</sup>
</details>
<br>


### 스태프 모드 활성화

일부 숨겨진 기능을 활성화하고 클라이언트를 스태프 모드로 설정합니다.

<details>
<summary>확장</summary>
 
이렇게 하면 클라이언트가 특정 플래그를 수정하여 Discord의 직원이라고 생각하도록 속이고 실험, 개발자 옵션 등에 액세스할 수 있습니다. (이 메뉴에서 미공개 Discord 업데이트를 받고, 다른 클라이언트를 에뮬레이션하고, 빌드 재정의를 생성하는 등의 작업을 할 수 있습니다.)

```js
wpRequire하자;
window.webpackChunkdiscord_app.push([[ Math.random() ], {}, (req) => { wpRequire = req; }]);
mod = Object.values(wpRequire.c).find(x => typeof x?.exports?.Z?.isDeveloper !== "정의되지 않음");
usermod = Object.values(wpRequire.c).find(x => x?.exports?.default?.getUsers)
노드 = Object.values(mod.exports.Z._dispatcher._actionHandlers._dependencyGraph.nodes)
노력하다 {
    nodes.find(x => x.name == "ExperimentStore").actionHandler["OVERLAY_INITIALIZE"]({사용자: {플래그: 1}})
} 잡기(e) {}
oldGetUser = usermod.exports.default.__proto__.getCurrentUser;
usermod.exports.default.__proto__.getCurrentUser = () => ({isStaff: () => true})
nodes.find(x => x.name == "DeveloperExperimentStore").actionHandler["CONNECTION_OPEN"]()
usermod.exports.default.__proto__.getCurrentUser = oldGetUser
```
<br>

![discorddevoptions](https://cdn.discordapp.com/attachments/788198099067076638/1004823296489029702/unknown.png)<br>
<sup>개발자 옵션 메뉴</sup>
</details>
<br>


### 모든 배지 받기

이 스크립트는 모든 배지를 로컬에서 제공하므로 사용자만 볼 수 있습니다.

<details>
<summary>확장</summary>

일부 배지는 특정 옵션이나 메뉴에 대한 액세스 권한을 부여합니다.<br>

```js
(() => {
    let 플래그 = {
        "DISCORD_EMPLOYEE": 1 << 0,
        "DISCORD_PARTNER": 1 << 1,
        "HYPESQUAD_EVENTS": 1 << 2,
        "BUG_HUNTER_LEVEL_1": 1 << 3,
        "HOUSE_BRAVERY": 1 << 6,
        "HOUSE_BRILLIANCE": 1 << 7,
        "하우스_밸런스": 1 << 8,
        "EARLY_SUPPORTER": 1 << 9,
        "BUG_HUNTER_LEVEL_2": 1 << 14,
        "VERIFIED_BOT_DEVELOPER": 1 << 17,
        "CERTIFIED_MODERATOR": 1 << 18,
        "ACTIVE_DEVELOPER": 1 << 22
    };
    
    webpackChunkdiscord_app.push([[Math.random()], {}, req => {
        for (Object.keys(req.c).map(x => req.c[x].exports).filter(x => x))의 const m {
            if (m.default && m.default.getCurrentUser !== 정의되지 않음) {
                return m.default.getCurrentUser().flags = Object.values(flags).reduce((pre, cur) => pre + cur, 0);
            }
        }
    }]);
})();
```
모든 배지를 받고 계정을 검역소에 두려면(시각적으로):
```js
webpackChunkdiscord_app.push([[Math.random()],{},(req)=>{for(const m of Object.keys(req.c).map((x)=>req.c[x]. exports).filter((x)=>x)){if(m.default&&m.default.getCurrentUser!==undefined){return m.default.getCurrentUser().flags=-1}}}]);
```
<br>

![미리보기](https://user-images.githubusercontent.com/55095883/110086787-191e1b00-7d93-11eb-8f0f-2b3a76210155.png)<br>
<sup>가짜 스크린샷이 아닙니다. 고객이 실제로 이를 표시할 것입니다.</sup>

![미리보기](https://cdn.discordapp.com/attachments/788198099067076638/1004823731056676954/unknown.png)
</details>
<br>


### 봇 및 시스템 태그

귀하가 봇 또는 Discord의 시스템인 것처럼 속입니다. (당신에게만 보입니다.)

<details>
<summary>확장</summary>

봇 태그 코드:
```js
window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x) ].exports).filter((x) => x)) {if (m.default && m.default.getCurrentUser !== 정의되지 않음) {return m.default.getCurrentUser().bot = true;}if (m .getCurrentUser !== 정의되지 않음) {return m.getCurrentUser().bot = true}}}])
```
확인된 봇 태그 코드:
```js
window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x) ].exports).filter((x) => x)) {if (m.default && m.default.getCurrentUser !== 정의되지 않음) {return m.default.getCurrentUser().bot = true;}if (m .getCurrentUser !== 정의되지 않음) {return m.getCurrentUser().bot = true}}}])
window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x) ].exports).filter((x) => x)) {if (m.default && m.default.getCurrentUser !== 정의되지 않음) {return m.default.getCurrentUser().isVerifiedBot = () => true; }if (m.getCurrentUser !== 정의되지 않음) {return m.getCurrentUser().isVerifiedBot = () => true}}}])
```
시스템 태그 코드:
```js
window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x) ].exports).filter((x) => x)) {if (m.default && m.default.getCurrentUser !== 정의되지 않음) {return m.default.getCurrentUser().isSystemUser = () => true; }if (m.getCurrentUser !== 정의되지 않음) {return m.getCurrentUser().isSystemUser = () => true}}}])
```
<br>

![grafik](https://user-images.githubusercontent.com/55095883/116669184-908cb700-a99e-11eb-9a7f-62c0d19e5486.png)<br>
<sup>시스템 배지를 사용하여 재미있는 가짜 공지 만들기</sup><br>

![grafik](https://user-images.githubusercontent.com/55095883/116669793-47893280-a99f-11eb-972d-bcc8e07c65dd.png)<br>
<sup>가짜 봇 배지</sup><br>

![grafik](https://user-images.githubusercontent.com/55095883/116669897-6982b500-a99f-11eb-8dfc-53caa1d312e3.png)<br>
<sup>봇 배지가 있는 사용자 팝아웃</sup>
</details>
<br>


### 간편 편집 모드

매번 요소 검사(CTRL + SHIFT + I)를 사용하지 않고도 이를 사용하여 가짜 스크린샷을 만들 수 있습니다.

<details>
<summary>확장</summary>

```js
document.designMode = '켜기'
```

</details>
<br>


### 무료 디스코드 니트로

Nitro를 구입하지 않고도 Nitro의 일부 기능을 사용할 수 있습니다.<br>
이것은 **중단**되고 패치되었습니다. [Discord Oxygen](https://github.com/hxr404/Discord-Oxygen)으로 대체되었습니다.

<details>
<summary>확장</summary>
 
Nitro가 있다고 생각하도록 고객을 속입니다. API 요청을 Nitro가 아닌 요청으로 변환하므로 Discord는 Nitro가 없다는 사실을 알아채지 못합니다.<br>
이 작업을 수행한다고 주장하는 스크립트에 각별히 주의하십시오. 이 스크립트는 유일하게 작동하는 스크립트입니다. 저나 이 저장소에서 직접 제공하지 않은 이 스크립트의 사본을 찾으면 저에게 신고해 주세요(사기일 수 있음).<br>
그림 이모티콘 처리 부분은 https://github.com/An00nymushun/DiscordFreeEmojis를 참조하세요.<br>
서버 측에서 실행되는 일부 기능은 시뮬레이션할 수 없으므로 모든 기능이 지원되는 것은 아닙니다.
애니메이션 이모티콘과 같은 기본 기능이 작동해야 합니다.

```js
/*
이것은 공개되어서는 안되기 때문에 코드를 제거했습니다. 사람들은 아무데나 복사하여 붙여넣기만 하면 나쁜 사람들이 백도어를 만들 것입니다.<br>
또한 Discord에서 이 문제를 수정하는 것을 원하지 않습니다.<br>

이 스크립트는 Discord Oxygen(https://github.com/hxr404/Discord-Oxygen)으로 대체되었습니다.
*/
```
<br>

![grafik](https://user-images.githubusercontent.com/55095883/116668188-5d95f380-a99d-11eb-96cf-a0e2dfc6bb23.png)<br>
<sup>구독 개요 페이지. 스크린샷에 사용된 계정은 Nitro를 **구매하지 않았습니다**.</sup>
</details>
<br>


### NSFW 채널 입력

18세 미만 계정에서 NSFW로 표시된 채널에 대한 액세스 권한을 부여합니다.<br>
**18세 이상인 경우에만 이 스크립트를 사용하세요! 해당 채널이 NSFW로 표시된 이유가 있습니다.**

<details>
<summary>확장</summary>

  이 스크립트는 계정이 미성년자로 잘못 표시된 18세 이상의 사람들과 인터넷에서 자신의 개인 데이터/ID를 공개하고 싶지 않은 사람들을 위한 것입니다. 다른 용도로 사용하지 마십시오.

```js
var findModule=(item)=>window.webpackChunkdiscord_app.push([[Math.random()],{},(req)=>{for(const m of Object.keys(req.c).map((x )=>req.c[x].exports).filter((x)=>x)){if(m.default&&m.default[item]!==undefined)return m.default}}])
findModule('getCurrentUser').getCurrentUser().nsfwAllowed = true
```
<br>

![그래픽](https://raw.githubusercontent.com/PndaBoi/pndaboi/main/6zsLEjYET0.png)<br>
<sup>스크립트를 실행하기 전에</sup><br>
<br>
  
![그래픽](https://raw.githubusercontent.com/PndaBoi/pndaboi/main/ypzEY7Yw0u.png)<br>
<sup>스크립트 실행 후</sup>
</details>
<br>


### 숨겨진 채널 ID 가져오기

클라이언트 수정 없이는 볼 수 없는 채널의 ID를 표시합니다.

<details>
<summary>확장</summary>

```js
window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x) ].exports).filter((x) => x)) {if (m.default && m.default.getPrivateChannelIds !== 정의되지 않음) {return console.log(m.default.getPrivateChannelIds())}if (m .getPrivateChannelIds !== 정의되지 않음) {return console.log(m.getPrivateChannelIds())}}}]);
```
<br>

![grafik](https://user-images.githubusercontent.com/55095883/116670257-cda57900-a99f-11eb-8f96-7d8d54754535.png)<br>
<sup>이 명령의 출력 예</sup>
</details>
<br>


### 비밀번호 변경

현재 로그인되어 있는 계정의 비밀번호를 변경합니다.<br>
**자신의 계정에서만 사용하세요! 계정 도용은 대부분의 국가에서 범죄입니다.**

<details>
<summary>확장</summary>

```js
let oldpassword = "";
let newpassword = "";

window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x) ].exports).filter((x) => x)) {if (m.default && m.default.getToken !== 정의되지 않음) {fetch("https://discord.com/api/v9/users/ @me", { "credentials": "include", "body": "{\"password\":\"" + oldpassword + "\",\"new_password\":\"" + newpassword + "\" }", "method": "PATCH", "headers": { "Authorization": m.default.getToken(), "Content-Type":"application/json" }}); return}if (m.getToken !== 정의되지 않음) {fetch("https://discord.com/api/v9/users/@me", {"credentials": "include","body": "{\"password\":\"" + oldpassword + "\",\"new_password\":\"" + newpassword + "\"}","method":"PATCH","headers": {"Authorization": m.getToken() , "콘텐츠 유형":"application/json"}});return}}}]);
```

</details>
<br>


### 길드 기능 추가

서버 기능(파트너 연결/검증된 서버 또는 일부 부스트 전용 기능 등)을 로컬에서 활성화하여 모든 것이 순전히 시각적임을 의미합니다.

<details>
<summary>확장</summary>

<img src="https://user-images.githubusercontent.com/55095883/121220849-4a702080-c885-11eb-965c-317749da0196.png"></img>
<img src="https://user-images.githubusercontent.com/55095883/121219947-7b9c2100-c884-11eb-99f1-e0a8525512a9.png"></img>
<img src="https://user-images.githubusercontent.com/55095883/121220469-e9484d00-c884-11eb-816f-2d3b9f46a585.png"></img>

유효한 기능은 'PARTNERED' 및 'VERIFIED'입니다.

```js
let serverid = "";
let 기능 = "";

window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x) ].exports).filter((x) => x)) {if (m.default && m.default.getGuilds !== 정의되지 않음) {return m.default.getGuild(serverid).features.add(기능)} if (m.getGuilds !== 정의되지 않음) {return m.getGuild(serverid).features.add(feature)}}}]);
```

</details>
<br>


### 웹훅 삭제

웹훅 URL을 사용하여 웹훅을 삭제합니다.<br>
이를 사용하여 토큰을 노리는 일부 사기꾼의 웹후크를 삭제할 수 있습니다. :)

<details>
<summary>확장</summary>

```js
let webhookURL = "PUT_WEBHOOK_URL_HERE";

가져오기를 기다립니다(webhookURL, {
  "방법": "삭제",
});
```

</details>
<br>


### 이메일 주소 및 전화번호 인증 우회

서버에서 이메일 주소 및 전화번호 확인을 우회합니다. 이렇게 하면 메시지를 보낼 수 없지만 음성 채널로 연결하고 대화할 수 있습니다.

<details>
<summary>확장</summary>


```js
window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x) ].exports).filter((x) => x)) {if (m.default && m.default.getCurrentUser !== 정의되지 않음) {return m.default.getCurrentUser().phone = '+1234567890';} if (m.getCurrentUser !== 정의되지 않음) {return m.getCurrentUser().phone = '+1234567890'}}}]);
window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x) ].exports).filter((x) => x)) {if (m.default && m.default.getCurrentUser !== 정의되지 않음) {return m.default.getCurrentUser().email = 'email@email.com ';}if (m.getCurrentUser !== 정의되지 않음) {return m.getCurrentUser().email = 'email@email.com'}}}]);
window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x) ].exports).filter((x) => x)) {if (m.default && m.default.getCurrentUser !== 정의되지 않음) {return m.default.getCurrentUser().verified = true;}if (m .getCurrentUser !== 정의되지 않음) {return m.getCurrentUser().verified = true}}}]);
```

</details>
<br>


### 디스코드 활동

현재 있는 음성 채널에 활동 버튼을 추가합니다.

<details>
<summary>확장</summary>

```js
var AppIds = ["755600276941176913", "880218394199220334", "755827207812677713", "773336526917861400", "814288819477020702", "832012774040141894", "879864070101172255", "879863881349087252", "832012854282158180", "878067389634314250", "902271654783242291", "879863686565621790 ", "879863976006127627", "852509694341283871", "832013003968348200", "832025144389533716", "763133495793942528", "880218832743055411", "878067427668275241", "879864010126786570", "879864104980979792", "891001866073296967", "832012586023256104", "832012682520428625", "832013108234289153", "763116274876022855", "832012730599735326", "832012938398400562", "832025061657280566", "801133024841957428", "832012815819604009", "832012894068801636", "832025114077298718", "832025993019260929"]
window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x) ].exports).filter((x) => x)) {if (m.default && m.default.getEnabledAppIds !== 정의되지 않음) {return m.default.getEnabledAppIds = () => AppIds}}}]) ;
```

<img src="https://i.ibb.co/rmskPSH/image.png"></img>
</details>
<br>


### 클라이언트 색상 변경

클라이언트의 색상을 원하는 대로 변경합니다.

<details>
<summary>확장</summary>

<br><img src="https://cdn.discordapp.com/attachments/841333120870645760/858800547958882334/unknown.png"></img>
알 수 없는 저자.

```js
__SECRET_EMOTION__.injectGlobal(`
    * {
--background-primary: #000000;
    --background-secondary: #000000;
--background-secondary-alt: #070707ff;
--background-accent: #252525;
--background-floating: #242424ff;
    --scrollbar-thin-track: #000000;
    --channeltextarea-background: #151515;
    }
`)
```

</details>
<br>


### 데스크톱 및 웹의 AMOLED 테마

일반 테마보다 어두운 색상을 사용하는 데스크톱 및 웹의 모바일에서 AMOLED 테마를 활성화합니다.

<details>
<summary>확장</summary>

```js
document.body.classList.add("theme-amoled");
```

</details>

</details>
<br>


## 프레임 워크

이제 별도의 저장소에서: https://github.com/hxr404/Discord-Oxygen

<details>
<summary>확장</summary>

프레임워크는 모든 콘솔 해킹을 단일 스크립트로 결합하는 새로운 프로젝트입니다.<br>
Discord 클라이언트(데스크톱 또는 웹)에 소스 코드(.js 파일)를 포함하기만 하면 됩니다.<br>
콘솔에 붙여넣기(CTRL + SHIFT + I, CTRL + V, ENTER)<br>
또는 사용자 스크립트로 추가합니다. (브라우저 확장이 필요합니다. Firefox의 경우 Firemonkey를 권장합니다.)<br>

### 작동 방식

프레임워크는 광범위한 API를 추가하고 BetterDiscord(+ Powercord) API를 추가할 계획이므로 프레임워크를 통해 BD 플러그인을 로드할 수 있습니다.<br>
모든 좋은 모드가 이미 설치되고 미리 구성되어 있다는 점을 제외하면 게임의 모드 로더와 유사합니다. (모드를 메인스트림에 병합하려면 풀 리퀘스트 또는 이슈를 여세요.)<br>
프레임워크는 모듈화되어 있으며 각 모듈은 이전 Nitro 해킹과 달리 자체 블록 범위에서 별도로 실행됩니다.
이것은 더 이상 하드코딩된 수정에 의존하지 않기 때문에 Discord가 수정하는 것을 방지할 것입니다.

### 역사

무료 Discord Nitro 핵은 매우 불안정했고 Discord는 이를 신속하게 수정했습니다. 그때부터 프레임워크 작업을 시작했습니다. 개선된 Discord Nitro였습니다.
훨씬 더 성능이 뛰어나고 더 나은 UX를 제공하며 개발이 더 쉬워졌습니다. 이전 Nitro 핵을 성공적으로 병합한 후 더 많은 기능으로 Nitro를 계속 개선했습니다. 그리고 생각했습니다. 왜 기본 Nitro 기능만 추가해야 할까요? 유용 할 수있는 훨씬 더 멋진 기능이 있습니다. The Framwerork는 모듈화되어 있기 때문에 다른 콘솔 해킹을 병합하는 데 약 5분이 걸렸습니다. 이렇게 새로운 프로젝트가 탄생했습니다.

</details>

## 라이선스
    저작권 (C) 2022 hxr404

    이 프로그램은 무료 소프트웨어입니다. 재배포 및/또는 수정할 수 있습니다.
    에 의해 게시된 GNU General Public License의 조건에 따라
    Free Software Foundation, 라이선스 버전 3 또는
    (귀하의 선택에 따라) 모든 최신 버전.

    이 프로그램은 도움이 되기를 바라며 배포합니다.
    그러나 어떠한 보증도 제공하지 않습니다. 묵시적 보증도 없이
    상품성 또는 특정 목적에의 적합성. 참조
    자세한 내용은 GNU General Public License를 참조하십시오.

    GNU General Public License 사본을 받았어야 합니다.
    이 프로그램과 함께. 그렇지 않은 경우 <https://www.gnu.org/licenses/>를 참조하십시오.
