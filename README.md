# b4x20220625
B4X實驗: jwt(JSON Web Token) ,B4X如何產生jwt token (B4J)
B4X實驗: jwt(JSON Web Token) ,B4X如何產生jwt token (B4J)


底下影片!!!工具網站介紹請參考這個!!!注意喔
https://www.youtube.com/watch?v=Jmg6lSst7jM  php&jwt(JSON Web Token) 如何產生jwt token


非常推薦!!!  成為看起來很強的後端~~~
https://www.youtube.com/watch?v=HMX4KSDtfpw&list=PLS5AiLcCHgNxd341NwuY9EOpVvY5Z8VOs


參考資料:
https://en.wikipedia.org/wiki/JSON_Web_Token
https://yami.io/jwt/
https://rbrt.wllr.info/2018/01/29/how-create-json-web-token-php.html
https://www.cnblogs.com/XiongMaoMengNan/p/6785155.html
http://www.ruanyifeng.com/blog/2018/07/json_web_token-tutorial.html
http://blog.objui.com/html/list_2030.html

工具網站
https://1024tools.com/hmac
https://1024tools.com/base64


https://www.b4x.com/android/forum/threads/jwt-solved.83395/#post-529147 只寫了部分.不完善!!!??
https://www.b4x.com/android/forum/threads/xui-sd-base64-encode-decode.105755/#content Base64編碼/解碼



jwt(JSON Web Token)
jwt Token 本身是不帶資訊的且無狀態性的（Stateless）



1.想使用JWT套件,用法在這裡
https://www.b4x.com/android/forum/threads/how-to-implement-jwt-on-b4j-web-server.71419/#post-454478



2.SHA256 演算法


// Token structure內容
header.payload.signature


// 真實的token
eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiYWRtaW4iOnRydWV9.TJVA95OrM7E2cBab30RMHrHDcEfxjoYZgeFONFh7HgQ


--------------------------------------
header表頭  json內容      {"alg":"HS256","typ":"JWT"}
{
 "alg": "HS256",
 "typ": "JWT"
}


base64Url Header=>
eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9

------------------------------------------
payload參數 json內容       {"sub":"1234567890","name":"John Doe","admin":true}
{
  "sub": "1234567890",
  "name": "John Doe",
  "admin": true
}

base64Url Payload=>
eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiYWRtaW4iOnRydWV9

-------------------------------------------
簽章
HMACSHA256(base64UrlEncode(header) + "." + base64UrlEncode(payload), "secret")


base64Url signature=>TJVA95OrM7E2cBab30RMHrHDcEfxjoYZgeFONFh7HgQ

jwt token=>eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiYWRtaW4iOnRydWV9.TJVA95OrM7E2cBab30RMHrHDcEfxjoYZgeFONFh7HgQ



3.下一個影片再介紹(去年說要做的,還沒實驗!!!這幾天 用B4X實作一下)
JWT的使用流程
•	初次登錄：使用者初次登錄，輸入用戶名密碼
•	密碼驗證：伺服器從資料庫取出用戶名和密碼進行驗證
•	生成JWT：伺服器端驗證通過，根據從資料庫返回的資訊，以及預設規則，生成JWT
•	返還JWT：伺服器的HTTP RESPONSE中將JWT返還
•	帶JWT的請求：以後用戶端發起請求，HTTP REQUEST
•	HEADER中的Authorizatio欄位都要有值，為JWT
•	服務器驗證JWT








