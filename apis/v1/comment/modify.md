# 댓글 수정 API

댓글/대댓글을 수정하는 API 입니다.

```
POST https://www.tistory.com/apis/comment/modify?
  access_token={access-token}
  &output={output-type}
  &blogName={blog-name}
  &postId={post-id}
  &parentId={parent-id}
  &commentId={comment-id}
  &content={content}
  &secret={secret}
```

기본 매개변수를 제외한 매개변수는 다음과 같습니다.

- blogName: Blog Name (필수)
- postId: 글 ID (필수)
- commentId: 댓글 ID (필수)
- parentId: 부모 댓글 ID (대댓글인 경우 사용)
- content: 댓글 내용
- secret: 비밀 댓글 여부 (1: 비밀댓글, 0: 공개댓글 - 기본 값)

## 응답

- commentUrl: 댓글 바로가기 링크

## 응답 예
```json
{
  "tistory":{
    "status":"200",
    "result":"OK",
    "commentUrl":"http://oauth.tistory.com/4#comment8176976"
  }
}
```
