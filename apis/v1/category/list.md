# 카테고리 목록 API

자신의 블로그 정보를 가져오는 API 입니다.

```
GET https://www.tistory.com/apis/category/list?
  access_token={access-token}
  &output={output-type}
  &blogName={blog-name}
```

기본 매개변수를 제외한 매개변수는 다음과 같습니다.

- blogName: Blog Name 입니다.

## 응답 item

- id: 카테고리 ID
- name: 카테고리 이름
- parent: 부모 카테고리 ID
- label: 부모 카테고리를 포함한 전체 이름 ('/'로 구분)
- entries: 카테고리내 글 수

## 응답값 예

```json
{
  "tistory":{
    "status":"200",
    "item":{
      "url":"oauth",
      "secondaryUrl":"",
      "categories":[
        {
          "id":"403929",
          "name":"OAuth2.0 Athentication",
          "parent":"",
          "label":"OAuth2.0 Athentication",
          "entries":"0"
        },
        {
          "id":"403930",
          "name":"Blog API Series",
          "parent":"",
          "label":"Blog API Series",
          "entries":"0"
        },
        ...
      ]
    }
  }
}
```
