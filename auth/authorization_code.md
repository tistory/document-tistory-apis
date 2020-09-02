# Authentication Code 방식

Server-side 프로그래밍으로 인증을 구현할 경우 사용하기 적합한 인증 방식입니다.

## 인증 요청 및 Authentication code 발급

사용자의 티스토리의 데이터 접근을 위해서 사용자에게 티스토리 인증요청을 합니다. 아래의 URL로 사용자가 접근하도록 하면 인증절차가 진행되며 사용자가 티스토리에 로그인하지 않은 경우 로그인 후에 인증 절차가 진행됩니다.

```
https://www.tistory.com/oauth/authorize?
  client_id={client-id}
  &redirect_uri={redirect-uri}
  &response_type=code
  &state={state-param}
```

매개변수는 다음과 같습니다.

- client_id: 클라이언트 정보의 Client ID 입니다.
- redirect_uri: 사용자가 인증 후에 리디렉션할 URI입니다. 클라이언트 정보의 Callback 경로로 등록하여야 하며 등록되지 않은 URI를 사용하는 경우 인증이 거부됩니다.
- response_type: 항상 `code`를 사용합니다.
- state:  [사이트간 요청 위조](https://en.wikipedia.org/wiki/Cross-site_request_forgery) 공격을 보호하기 위한 임의의 고유한 문자열이며 리디렉션시 해당 값이 전달됩니다. (필수아님)

### 예

인증요청 URI가 다음과 같은 경우

```
https://www.tistory.com/oauth/authorize?
  client_id=abcdefghijklmnopqrstuvwxyz
  &redirect_uri=http://client.redirect.uri
  &response_type=code
  &state=someValue
```

인증 완료후 다음과 같이 리디렉션됩니다.

```
http://client.redirect.uri?code=authorizationCode&state=someValue
```

## 리디렉션 처리

사용자가 인증을 완료하면 code와 함께 다음의 URI로 리디렉션됩니다.

```
{redirect-uri}?
  code={authorization-code}
  &state={state-param}
```

매개변수는 다음과 같습니다.

- code: 티스토리가 발급하는 Authorization code로 Access Token을 발급받는데 사용합니다. 발급된 code는 1시간 이내에만 사용가능하며 재사용 할 수 없습니다.
- state: 인증요청시 전달한 값입니다. 이 값을 통해 요청이 변조되었는지 검사합니다.


### 오류

오류가 발생한 경우 오류정보와 함께 redirect_uri로 리디렉션됩니다.

```
{redirect-uri}?
  error={error}
  &error_reason={error-reason}
  &state={state-param}
```

매개변수는 다음과 같습니다.

- error: 에러 코드입니다. 자세한 내용은 [OAuth 2.0 명세](https://tools.ietf.org/html/rfc6749#section-4.1.2.1)에 정의되어 있습니다.
- error_reason: 에러에 대한 설명입니다.
- state: 인증요청시 전달한 값입니다. 이 값을 통해 요청이 변조되었는지 검사합니다.

## Access Token 발급

다음의 URL을 사용해 발급된 code를 Access Token과 교환합니다. 이때 Secret Key가 사용되므로 반드시 서버에서 수행해야합니다.

```
GET https://www.tistory.com/oauth/access_token?
  client_id={client-id}
  &client_secret={client-secret}
  &redirect_uri={redirect-uri}
  &code={code}
  &grant_type=authorization_code
```

매개변수는 다음과 같습니다.

- client_id: 클라이언트 정보의 Client ID 입니다.
- client_secret: 클라이언트 정보의 Secret Key 입니다. 이 정보는 티스토리와 Client만이 공유해야하며 절대 외부에 공개되면 안됩니다.
- redirect_uri: 인증요청시 사용한 리디렉션 URL로 요청검증을 위해 사용합니다.
- code: 리디렉션으로 전달받은 code를 그대로 사용합니다.
- grant_type: 항상 `authorization_code`를 사용합니다.

발급요청이 성공한 경우 HTTP 200 응답과 함께 Access Token이 응답값으로 옵니다.

```
{access-token}
```

### 오류

오류가 발생한 경우 HTTP 오류 응답과 함께 오류 메시지가 응답값으로 옵니다. 응답값은 다음과 같습니다.

```
error={error}&error_description={error-description}
```

- error: 에러코드입니다.
- error_description: 에러에 대한 설명입니다.
