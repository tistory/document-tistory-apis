# 게시글 댓글 목록 API

게시글 댓글 목록을 가져오는 API 입니다.

```
GET https://www.tistory.com/apis/comment/list?
  access_token={access-token}
  &output={output-type}
  &blogName={blog-name}
  &postId={post-id}
```

기본 매개변수를 제외한 매개변수는 다음과 같습니다.

- blogName: Blog Name 입니다.
- postId: 글 ID

## 응답 item

- id: 댓글 ID
- date: 댓글 작성시간 (TIMESTAMP)
- name: 작성자 이름
- parentId: 부모 댓글 ID (대댓글인 경우만 사용)
- homepage: 작성자 홈페이지 주소
- visibility: 승인 여부 (0: 승인대기, 2: 승인)
- comment: 댓글 내용
- open: 댓글 공개여부 (Y: 공개, N: 비공개)

## 응답값 예

```json
{
  "tistory": {
    "status": "200",
    "item": {
      "url": "http://oauth.tistory.com/4",
      "secondaryUrl": "",
      "postId": "4",
      "totalCount": "3",
      "comments": {
        "comment": [
          {
            "id": "8176918",
            "date": "1303796711",
            "name": "지나다가",
            "parentId": "",
            "homepage": "http://someurl.com",
            "visibility": "2",
            "comment": "좋은 글 감사합니다.",
            "open": "Y"
          },
          {
            "id": "8176923",
            "date": "1303796801",
            "name": "글쎄요",
            "parentId": "",
            "homepage": "http://shesgone.com",
            "visibility": "2",
            "comment": " 제 홈에 와서 구경해보세요^_^",
            "open": "N"
          },
          {
            "id": "8176926",
            "date": "1303796900",
            "name": "Tistory API",
            "parentId": "8176918",
            "homepage": "http://oauth.tistory.com",
            "visibility": "2",
            "comment": "비루한 글에 칭찬을 하시니 몸둘바를 모르.. 지 않아!",
            "open": "Y"
          }
        ]
      }
    }
  }
}
```
