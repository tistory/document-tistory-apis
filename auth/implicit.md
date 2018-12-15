# Implicit 방식

Client-side 프로그래밍으로 인증을 구현할 경우 사용하기 적합한 인증 방식입니다. Javascript 등을 이용해 클라이언트 브라우저등에서만 모든 처리가 이루어지는 요청에 활용할수 있습니다.

## 인증 요청 및 Authentication code 발급

사용자의 티스토리의 데이터 접근을 위해서 사용자에게 티스토리 인증요청을 합니다. 아래의 URL로 사용자가 접근하도록 하면 인증절차가 진행되며 사용자가 티스토리에 로그인하지 않은 경우 로그인 후에 인증 절차가 진행됩니다.

```
https://www.tistory.com/oauth/authorize?
  client_id={client-id}
  &redirect_uri={redirect-uri}
  &response_type=token
```

매개변수는 다음과 같습니다.

- client_id: 클라이언트 정보의 Client ID 입니다.
- redirect_uri: 사용자가 인증 후에 리디렉션할 URL입니다. 클라이언트 정보의 Callback 경로로 등록하여야 하며 등록되지 않은 URL을 사용하는 경우 인증이 거부됩니다.
- response_type: Authorization code 방식과 구분하기 위해 사용하며 항상 `token`를 사용합니다.

### 예

인증요청 URL이 다음과 같은 경우

```
https://www.tistory.com/oauth/authorize?
  client_id=abcdefghijklmnopqrstuvwxyz
  &redirect_uri=http://client.redirect.url
  &response_type=token
```

인증 완료후 다음과 같이 리디렉션됩니다.

```
http://client.redirect.url#accesss_token={access-token}&expires_in=3600
```

## 리디렉션 처리 및 Access Token 발급

사용자가 인증을 완료하면 다음의 URL로 리디렉션됩니다.

```
{redirect-uri}#
  accesss_token={access-token}
  &expires_in=3600
```

Implicit 방식은 인증 완료 후 Access Token이 즉시 발급됩니다. 매개변수와 같은 형식으로 아래와 같이 해쉬로 전달됩니다. 브라우저를 통해 Access Token이 발급되므로 외부에 노출되지 않도록 주의가 필요합니다.

- access_token: 발급된 Access Token 입니다.
- expires_in: Access Token의 유효시간으로 초단위입니다.
