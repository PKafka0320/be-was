## 1. 학습 목표

- HTTP GET 프로토콜을 이해한다.
- HTTP GET에서 parameter를 전달하고 처리하는 방법을 학습한다.
- HTTP 클라이언트에서 전달받은 값을 서버에서 처리하는 방법을 학습한다.

---

## 2. 기능 요구사항

- GET으로 회원가입 기능 구현

---

## 3. 학습 내용

### 1. HTTP GET Method

- GET 메서드
  > HTTP GET 요청 메서드는 서버로부터 자원을 요청하는 데 사용됩니다.
  > <br>GET 요청은 데이터를 가져올 때만 사용해야 하며 서버는 상태를 변경하면 안 됩니다. 

- Query Parameter
  > GET /user/create?`userId=id&password=pwd&name=user&email=user@email`
  > 
  > 쿼리 파라미터는 GET 요청을 하면서 파라미터를 서버에 보내줄 수 있는 방법입니다.
  > <br>주소와 쿼리 파라미터는 `?`로 구분됩니다.
  > <br>파라미터는 `{key}={value}` 형태로 작성하며, `&`를 사용하여 구분합니다.

---

## 4. 문제 해결

- HTTP Redirect
  > 회원가입 요청을 처리하고 메인 페이지로 이동하도록 했지만
  > 메인 페이지 이동 후 다른 페이지로 이동하지 못하는 문제가 발생했습니다.

  > redirect 헤더를 만들어주는 함수를 만들어 브라우저가 302 응답을 받고,
  > 홈 URL로 페이지 재요청을 하도록 하여 해결했습니다. 

---

## 5. 기록

[HTTP GET Method](http/get-method.md)

[HTTP Redirect](http/redirect.md)

---

## 6. 참고 문서

[REQBIN - GET Method](https://reqbin.com/Article/HttpGet)

[MDN - Redirections in HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP/Redirections)