# 최근 댓글 목록 API

최근 댓글 목록을 가져오는 API 입니다.

```
GET https://www.tistory.com/apis/comment/newest?
  access_token={access-token}
  &output={output-type}
  &blogName={blog-name}
  &page={page}
  &count={count}
```

기본 매개변수를 제외한 매개변수는 다음과 같습니다.

- blogName: Blog Name 입니다.
- page: 가져올 페이지 (기본값: 1)
- count: 페이지당 댓글 수 (기본값: 10, 최대값: 10)

## 응답 item

- id: 댓글 ID
- date: 댓글 작성시간 (TIMESTAMP)
- postId: 작성된 글 ID
- name: 작성자 이름
- homepage: 작성자 홈페이지 주소
- comment: 댓글 내용
- open: 댓글 공개여부 (Y: 공개, N: 비공개)

## 응답값 예

```json
{
  "tistory":{
    "status":"200",
    "item":{
      "url":"http://oauth.tistory.com",
      "secondaryUrl":"",
      "comments":{
        "comment":[
          {
            "id":"8176926",
            "date":"1303796900",
            "postId":"4",
            "name":"Tistory API",
            "homepage":"http://oauth.tistory.com",
            "comment":"비루한 글에 칭찬을 하시니 몸둘바를 모르.. 지 않아!",
            "open":"Y"
          },
          {
            "id":"8176923",
            "date":"1303796801",
            "postId":"4",
            "name":"글쎄 요",
            "homepage":"http://shesgone.com",
            "comment":"제 홈에 와서 구경해보세요^_^",
            "open":"N"
          },
          {
            "id":"8176918",
            "date":"1303796711",
            "postId":"4",
            "name":"지나다가",
            "homepage":"http://someurl.com",
            "comment":"좋은 글 감사합니다.",
            "open":"Y"
          }
        ]
      }
    }
  }
}
```
