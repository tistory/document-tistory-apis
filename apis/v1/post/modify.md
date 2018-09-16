# 글 수정 API

블로그에 글을 작성하는 API 입니다.

```
POST https://www.tistory.com/apis/post/modify?
  access_token={access-token}
  &output={output-type}
  &blogName={blog-name}
  &postId={post-id}
  &title={title}
  &content={content}
  &visibility={visibility}
  &category={category-id}
  &published={published}
  &slogan={slogan}
  &tag={tag}
  &acceptComment={acceptComment}
  &password={password}
```

기본 매개변수를 제외한 매개변수는 다음과 같습니다.

- blogName: Blog Name (필수)
- postId: 글 번호 (필수)
- title: 글 제목 (필수)
- content: 글 내용
- visibility: 발행상태 (0: 비공개 - 기본값, 1: 보호, 3: 발행)
- category: 카테고리 아이디 (기본값: 0)
- published: 발행시간 (TIMESTAMP 이며 미래의 시간을 넣을 경우 예약. 기본값: 현재시간)
- slogan: 문자 주소
- tag: 태그 (',' 로 구분)
- acceptComment: 댓글 허용 (0, 1 - 기본값)
- password: 보호글 비밀번호

## 응답

- postId: 글 번호
- url: 발행 주소

## 응답 예
```json
{
  "tistory":{
    "status":"200",
    "postId":"74",
    "url":"http://sampleUrl.tistory.com/74"
  }
}
```
