# 글 목록 API

블로그 글 목록를 가져오는 API 입니다.

```
GET https://www.tistory.com/apis/post/list?
  access_token={access-token}
  &output={output-type}
  &blogName={blog-name}
  &page={page-number}
```

기본 매개변수를 제외한 매개변수는 다음과 같습니다.

- blogName: Blog Name 입니다.
- page: 불러올 페이지 번호입니다.

## 응답 item

- url: 티스토리 기본 url
- secondaryUrl: 독립도메인 url
- page: 현재 페이지
- count: 페이지의 글 개수
- totalCount: 전체 글 수
- posts: 글 리스트
  - id: 글 ID
  - title: 글 제목
  - postUrl: 글 대표 주소
  - visibility: 글 공개 단계 (0: 비공개, 15: 보호, 20: 발행)
  - categoryId: 카테고리 ID
  - comments: 댓글 수
  - trackbacks: 트랙백 수
  - date: YYYY-mm-dd HH:MM:SS

## 응답값 예

```json
{
  "tistory": {
    "status": "200",
    "item": {
      "url": "http://oauth-test.tistory.com",
      "secondaryUrl": "",
      "page": "1",
      "count": "10",
      "totalCount": "181",
      "posts": [
        {
          "id": "201",
          "title": "테스트 입니다.",
          "postUrl": "http://oauth-test.tistory.com/201",
          "visibility": "0",
          "categoryId": "0",
          "comments": "0",
          "trackbacks": "0",
          "date": "2018-06-01 17:54:28"
        },
        ...
      ]
    }
  }
}
```
