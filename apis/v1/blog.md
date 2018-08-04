# 블로그 정보 API

자신의 블로그 정보를 가져오는 API 입니다.

```
GET https://www.tistory.com/apis/blog/info?
  access_token={access-token}
  &output={output-type}
```

## 응답 item

- id: 사용자 로그인 아이디
- userId: 사용자 id
- blogs
  - url: 티스토리 기본 url
  - secondaryUrl: 독립도메인 url
  - title: 블로그 타이틀
  - description: 블로그 설명
  - default: 대표블로그 여부 (Y/N)
  - blogIconUrl: 블로그 아이콘 URL
  - faviconUrl: 파비콘 URL
  - profileThumbnailImageUrl: 대표이미지 썸네일 URL
  - profileImageUrl: 대표이미지 URL
  - blogId: 블로그 아이디
  - nickname: 블로그에서의 닉네임
  - role: 블로그 권한
  - statistics: 블로그 컨텐츠 개수
    - post: 글 수
    - comment: 댓글 수
    - trackback: 트랙백 수
    - guestbook: 방명록 수
    - invitation: 초대장 수

## 응답값 예

### XML

```xml
<?xml version="1.0" encoding="utf-8"?>
<tistory>
  <status>200</status>
  <item>
    <id>blog_oauth_test@daum.net</id>
    <userId>12345</userId>
    <blogs>
      <blog>
        <name>oauth-test</name>
        <url>http://oauth-test.tistory.com</url>
        <secondaryUrl>http://</secondaryUrl>
        <nickname>티스토리 테스트</nickname>
        <title>테스트 블로그 1</title>
        <description>안녕하세요! 티스토리입니다.</description>
        <default>Y</default>
        <blogIconUrl>https://blog_icon_url</blogIconUrl>
        <faviconUrl>https://favicon_url</faviconUrl>
        <profileThumbnailImageUrl>https://profile_image</profileThumbnailImageUrl>
        <profileImageUrl>https://profile_image</profileImageUrl>
        <role>소유자</role>
        <blogId>123</blogId>
        <statistics>
          <post>182</post>
          <comment>146</comment>
          <trackback>0</trackback>
          <guestbook>39</guestbook>
          <invitation>0</invitation>
        </statistics>
      </blog>
      ...
    </blogs>
  </item>
</tistory>
```

### JSON

```json
{
  "tistory": {
    "status": "200",
    "item": {
      "id": "blog_oauth_test@daum.net",
      "userId": "12345",
      "blogs": [
        {
          "name": "oauth-test",
          "url": "http://oauth-test.tistory.com",
          "secondaryUrl": "http://",
          "nickname": "티스토리 테스트",
          "title": "테스트 블로그 1",
          "description": "안녕하세요! 티스토리입니다.",
          "default": "Y",
          "blogIconUrl": "https://blog_icon_url",
          "faviconUrl": "https://favicon_url",
          "profileThumbnailImageUrl": "https://profile_image",
          "profileImageUrl": "https://profile_image",
          "role": "소유자",
          "blogId": "123",
          "statistics": {
            "post": "182",
            "comment": "146",
            "trackback": "0",
            "guestbook": "39",
            "invitation": "0"
          }
        },
        ...
      ]
    }
  }
}
```
