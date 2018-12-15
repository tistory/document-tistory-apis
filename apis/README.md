# Open API 소개

티스토리 Open API는 다음과 같은 형태의 URL로 제공됩니다.

```
https://www.tistory.com/apis/{RESOURCE}?
  access_token={access-token}
  &output={output-type}
```

매개변수는 다음과 같습니다.

- access_token: 발급받은 Access Token 입니다.
- output: xml, json 두가지 형태의 응답형식을 지정하며 생략가능합니다. 생략할 경우 요청해더의 'Content-Type'을 보고 응답형식을 결정하며 기본 값은 xml입니다.

## 예

카테고리 리스트를 xml로 가져올 때
```
https://www.tistory.com/apis/category/list?
  access_token=abcdefghijklmnopqrstuvwxyz
```

두번째 페이지의 글 리스트를 json으로 가져올 때
```
https://www.tistory.com/apis/post/list?
  access_token=abcdefghijklmnopqrstuvwxyz
  &page=2
  &output=json
```

## 응답 예

JSON 응답
```json
{
  "tistory": {
    "status": "[결과 CODE]",
    "item": "[DATA]",
    "error_message": "[오류 발생시에만 사용]"
  }
}
```

XML 응답
```xml
<tistory>
  <status>[결과 CODE]</status>
	<item>[DATA]</item>
  <error_message>[오류 발생시에만 사용]</error_message>
</tistory>
```
