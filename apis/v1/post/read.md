# 글 읽기 API

```
GET https://www.tistory.com/apis/post/read?
  access_token={access-token}
  &blogName={blog-name}
  &postId={post-id}
```

기본 매개변수를 제외한 매개변수는 다음과 같습니다.

- blogName: Blog Name 입니다.
- postId: 글 ID

## 응답 item

- url
- secondaryUrl
- id: 글 ID
- title: 글 제목
- content: 내용
- categoryId: 카테고리 ID
- postUrl: 글 대표주소
- visibility: 글 공개 단계
- acceptComment: 댓글 허용 여부(허용: 1, 비허용: 0)
- tags
  - tag: 태그
- comments: 댓글 개수
- date: 발행시간 timestamp

## 응답 예

```
{
  "tistory":{
    "status":"200",
    "item":{
      "url":"http://oauth.tistory.com",
      "secondaryUrl":"",
      "id":"1",
      "title":"티스토리 OAuth2.0 API 오픈!",
      "content":"안녕하세요 Tistory API 입니다.<br><br>이번에 Third-party Developer 용 <b>Tistory OAuth 2.0 API</b> 가 오픈됩니다.<br>Tistory 회원이라면, 여러분의 모든 app에 자유롭게 활용하실 수 있습니다.<br><br><div class="\"imageblock" center\"="" style="\"text-align:" center;="" clear:="" both;\"=""><img src="\"http://cfile10.uf.tistory.com/image/156987414DAF9799227B34\""></div><br><p></p>많은 기대와 사랑 부탁드립니다. <br> ",
      "categoryId":"0",
      "postUrl":"http://oauth.tistory.com/1",
      "visibility":"0",
      "acceptComment":"1",
      "acceptTrackback":"1",
      "tags":{
        "tag":["open", "api"]
      },
      "comments":"0",
      "trackbacks":"0",
      "date":"1303352668"
    }
  }
}
```
