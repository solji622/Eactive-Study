# HTTP 상태 코드 (HTTP Status Code)
<br>
<br>

## 📌 HTTP 상태 코드란?
특정 HTTP 요청의 성공 유무를 서버에서 알려주는 숫자 코드 <br>
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
<Br>
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

![teapot](https://github.com/solji622/LevelUp-Study/blob/86552272dbcdb16bdf5cf94f66076ef7337f9670/25.04/HTTP%20Status%20Code/asset/418_teapot.png)

418은 커피 주전자용 프로토콜(Hyper Text Coffee Pot Control Protocol, HTCPCP)에서 비롯되었다. <br>
클라이언트가 찻 주전자에게 커피를 끓여달라는 요청을 하였을 때의 에러 코드로 <br>
HTCPCP의 메소드 BREW를 서버에게 요청했을 때 나타난다. <br>


 
