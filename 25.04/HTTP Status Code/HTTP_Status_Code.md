
# HTTP 상태 코드 (HTTP Status Code)
<br>
<br>

## 📌 HTTP 상태 코드란?
특정 HTTP 요청의 성공 유무를 서버에서 알려주는 숫자 코드 <br>
<br>

<img src="https://github.com/solji622/LevelUp-Study/blob/d06506ba3a1bc3524f95e22cdcdc29d8701f80ac/25.04/HTTP%20Status%20Code/asset/exam.png" width="50%"><br>
<br>
![개발자 도구 네트워크탭](https://github.com/solji622/LevelUp-Study/blob/bf5dbf52c3ec2b66790d9cca0eddf24e2fd86ff5/25.04/HTTP%20Status%20Code/asset/chromeNetwork.png)
<br>
크롬 개발자 도구의 네트워크 탭을 보면 사진처럼 숫자 코드로 요청 결과를 간략하게 보여주기도 한다 <br>

3자리 숫자로 이루어져 있으며 총 다섯가지로 나누어진다
> **1XX** : 정보 (Informational) <br>
> **2XX** : 성공 (Success) <br>
> **3XX** : 리다이렉션 (Redirection) <br>
> **4XX** : 클라이언트 에러 (Client Error) <br>
> **5XX** : 서버 에러 (Server Error) <br>

<br>
<br>
<br>

## 📌 1XX [Informational]
> 정보 제공, 요청이 수신되어 처리 중 <br>
현업에서도 잘 사용되지 않는 상태코드이다. <br>

|status code|message|desc|
|:---|:---|:---|
|100|Continue|요청이 처리 됨|
|101|Switching Protocol|서버의 프로토콜 전환|
|102|Processing|요청 처리 중, 제대로 된 응답 불가|
|103|Early Hints|웹페이지 리소스 사전 로드|

<br>
<Br>
<br>

## 📌 2XX [Success]
> 성공, 요청이 정상적으로 처리 되었다는 의미다 <br>
표에 있는 것 외에도 203, 206-8, 218, 226이 존재한다 <br>

|status code|message|desc|
|:---|:---|:---|
|200|Ok|요청이 정상적으로 처리됨|
|201|Created|요청 처리가 완료되었고 새 리소스가 생성됨|
|202|Accepted|요청은 받았으나 크고 무거워 아직 처리가 완료되지 않음|
|204|No Content|정상적인 요청이나 제공할 콘텐츠가 존재하지 않음|
|205|Reset Content|요청을 보낸 뷰를 리셋, 즉 브라우저 새로고침하기|

<br>
<Br>
<br>

## 📌 3XX [Redirection]
> 리다이렉션(다른 URL 다시 지시), 요청 완료 시 추가 작업이 필요함 <br>
305, 306은 보안 문제로 지원이 중단되어 더이상 사용되지 않는다 <br>

|status code|message|desc|
|:---|:---|:---|
|300|Multiple Choice|요청에 대한 하나 이상의 응답이 가능함|
|301|Moved Permanently|요청한 리소스의 URL이 **영구적으로** 변경됨|
|302|Found|요청한 리소스의 URL이 **일시적으로** 변경됨|
|303|See Other|다른 URL에서 GET 요청을 통해 요청했던 리소스를 찾음|
|304|Not Modified|응답 수정 되지 않아 최신 상태이므로 캐시를 이용함|
|307|Temporary Redirect|요청이 **일시적으로** 다른 URL에 존재함|
|308|Permanent Redirect|요청이 **영구적으로** 다른 URL에 존재함|

<br>
<br>

### ❓ 일시적으로, 영구적으로
|status code|message|method|
|:---|:---|:---|
|301|Moved Permanently|유지 X (POST → GET)|
|302|Found|유지 X (POST → GET)|
|307|Temporary Redirect|유지 (POST)|
|308|Permanent Redirect|유지 (POST)|

일시적, 영구적 리다이렉션은 리다이렉션의 속성이다.
> 일시적 리다이렉션 : 리소스 위치 잠깐 변경, 클라이언트는 다음에도 기존 주소로 요청 <br>
> 영구적 리다이렉션 : 리소스 위치 완전 변경, 클라이언트는 다음에 새로운 주소로 요청

비유를 한다면 **이사 가냐, 출장 가냐**의 차이라 할 수 있다. <br>
이때 301 & 302는 가는 방식이 바뀔 수 있고 <br>
307 & 308은 가는 방식이 그대로 유지되는 점에서 다르다고 볼 수 있다.<br>

<br>
<Br>
<br>
<br>

## 📌 4XX [Client Error]
> 클라이언트 오류, 문법 오류 등으로 인해 요청 수행이 불가능하며 원인은 클라이언트에게 있다 <br>
표에 있는 것 외에도 402, 409, 411-29, 431, 451 등이 있다 <Br>

|status code|message|desc|
|:---|:---|:---|
|400|Bad Request|클라이언트가 잘못된 요청을 보냄 (주로 문법 오류)|
|401|Unauthorized|인증된 요청자가 아니기에 요청을 수행할 수 없음|
|403|Forbidden|클라이언트는 콘텐츠에 접근할 권리가 없음 <br> (승인되지 않은 요청자, 401과 달리 서버가 요청자가 누군지 알고 있음)|
|404|Not Found|서버가 요청받은 리소스를 찾을 수 없음|
|405|Method Not Allowed|요청이 허용되지 않은 메소드(기능 제한/금지로 인하여)|
|408|Request Timeout|요청이 너무 커 처리 시간 초과로 인해 연결이 끊김|
|410|Gone|리소스가 영구적으로 삭제되고 전달해 줄 주소도 존재하지 않음|
|418|I’m a teapot|서버는 커피를 찻 주전자에 끓이는 것을 거절합니다.|
<br>

## ❓ 418 I'm a teapot?
국제 인터넷 표준화 기구(Internet Engineering Task Force, IETF)에서 만우절 장난으로 나온 상태 코드다. <br>
매년 만우절에 장난으로 기술문서인 RFC를 출판하는데, 418은 1998년에 출판된 RFC 내용의 일부다. <br>

<img src="https://github.com/solji622/LevelUp-Study/blob/86552272dbcdb16bdf5cf94f66076ef7337f9670/25.04/HTTP%20Status%20Code/asset/418_teapot.png" width="70%"/>

418은 커피 주전자용 프로토콜(Hyper Text Coffee Pot Control Protocol, HTCPCP)에서 비롯되었다. <br>
클라이언트가 찻 주전자에게 커피를 끓여달라는 요청을 하였을 때의 에러 코드로 <br>
HTCPCP의 메소드 BREW를 서버에게 요청했을 때 나타난다. <br>

구글에서 https://www.google.com/teapot 에 접속하면 실제로 418을 보여준다! <br>
![이스터에그](https://github.com/solji622/LevelUp-Study/blob/745f967e1249cddf9c0e881425627100934f8a5e/25.04/HTTP%20Status%20Code/asset/google.gif)

또한 body가 "short and stout."인 이유는 *I'm A Little Teapot Song* 의 가사에서 가져왔기 때문이다. <br>
<br>
<img src="https://github.com/solji622/LevelUp-Study/blob/745f967e1249cddf9c0e881425627100934f8a5e/25.04/HTTP%20Status%20Code/asset/song.png" width="70%"/>

<br>
<Br>
<br>
<br>

## 📌 5XX [Server Error]
> 서버 오류, 4XX와 동일하게 문법 오류로 인한 것이나 원인은 서버에게 있다 <br>
4XX는 요청 메시지 수정 후 재전송으로 해결이 가능하지만<Br>
5XX는 서버 문제로 서버 자체의 상태를 확인해야만 해결이 가능하다<br>
표에 있는 것 외에도 비공식으로 506, 510, 599가 있다 <br>

|status code|message|desc|
|:---|:---|:---|
|500|Internal Server Error|서버 내부 문제 발생, 처리가 불가능함|
|501|Not Implemented|요청에 대해 구현되지 않았음, 서버가 지원하지 않아 처리가 불가능함|
|502|Bad Gateway|게이트웨이가 잘못되어, 서버가 잘못된 응답을 수신함 <br> (ex. 접속 폭주로 인한 통신 장애)|
|503|Service Unavailable|서버가 요청을 처리할 준비가 되지 않음 (서비스 이용 불가)|
|504|Gateway Timeout|게이트웨이 시간 초과, 요청 처리를 중단하고 연결을 끊음|
|505|HTTP Version Not Supported|서버에서 지원되지 않는 HTTP 버전|
|511|Network Authentication Required|네트워크 인증 요구|
<br>

<br>
<Br>
<br>
<br>

## 💡 그 외..
https://http.cat/ 에 접속하여 주소창에 `https://http.cat/[status_code]` 를 입력하면 에러 코드를 고양이짤로 표현해준다 <br>
<br>
<img src="https://github.com/solji622/LevelUp-Study/blob/9b3353c81414bfb055070faff862a1f6ef52d97f/25.04/HTTP%20Status%20Code/asset/HTTP_CAT.png" width="70%">



 
