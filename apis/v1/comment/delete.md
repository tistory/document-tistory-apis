# 댓글 수정 API

댓글/대댓글을 수정하는 API 입니다.

```
POST https://www.tistory.com/apis/comment/delete?
  access_token={access-token}
  &output={output-type}
  &blogName={blog-name}
  &postId={post-id}
  &commentId={comment-id}
```

기본 매개변수를 제외한 매개변수는 다음과 같습니다.

- blogName: Blog Name (필수)
- postId: 글 ID (필수)
- commentId: 댓글 ID (필수)

## 응답 예
```json
{
  "tistory":{
    "status":"200",
  }
}
```
