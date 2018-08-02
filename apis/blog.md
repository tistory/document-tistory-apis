# 블로그 정보 API

블로그 정보를 가져오는 API 입니다.

```
https://www.tistory.com/apis/blog/info?
  access_token={access-token}
  &output={output-type}
  &name={blog-name}
```

기본 매개변수를 제외한 매개변수는 다음과 같습니다.

- name: 조회하고자 하는 blog name입니다. 티스토리 주소중 `.tistory.com`을 제외한 부분이 blog name입니다. `notice.tistory.com` 에서는 `notice` 입니다.

## 응답값 예

### XML

```xml
<?xml version="1.0" encoding="utf-8"?>
<tistory>
    <status>200</status>
    <id>blogtest_080@hanmail.net</id>
    <item>
        <url>http://oauth.tistory.com</url>
        <secondaryUrl>http://</secondaryUrl>
        <nickname><![CDATA[Tistory API]]></nickname>
        <title><![CDATA[나만의 앱, Tistory OAuth API 로 만들어보세요!]]></title>
        <description><![CDATA[]]></description>
        <default>Y</default>
        <blogIconUrl>http://i1.daumcdn.net/cfs.tistory/blog/79/795307/index.gif</blogIconUrl>
        <faviconUrl>http://i1.daumcdn.net/cfs.tistory/blog/79/795307/index.ico</faviconUrl>
        <profileThumbnailImageUrl>http://cfile1.uf.tistory.com/R106x0/1851DB584DAF942950AF29</profileThumbnailImageUrl>
        <profileImageUrl>http://cfile1.uf.tistory.com/R106x0/1851DB584DAF942950AF29</profileImageUrl>
        <blogId>795307</blogId>
        <statistics>
            <post>3</post>
            <comment>0</comment>
            <trackback>0</trackback>
            <guestbook>0</guestbook>
            <invitation>0</invitation>
        </statistics>
    </item>
    <item>
        <url>http://oauth2.tistory.com</url>
        <secondaryUrl>http://</secondaryUrl>
        <nickname><![CDATA[Tistory API]]></nickname>
        <title><![CDATA[나만의 비밀 홈]]></title>
        <description><![CDATA[]]></description>
        <default>N</default>
        <blogIconUrl>http://i1.daumcdn.net/cfs.tistory/blog/79/795308/index.gif</blogIconUrl>
        <faviconUrl>http://i1.daumcdn.net/cfs.tistory/blog/79/795308/index.ico</faviconUrl>
        <profileThumbnailImageUrl></profileThumbnailImageUrl>
        <profileImageUrl></profileImageUrl>
        <statistics>
            <post>0</post>
            <comment>0</comment>
            <trackback>0</trackback>
            <guestbook>0</guestbook>
            <invitation>0</invitation>
        </statistics>
    </item>
</tistory>
```

### JSON

```json
{
    "tistory":{
        "status":"200",
        "id":"blogtest_080@hanmail.net",
        "item": [
            {
                "url":"http://oauth.tistory.com",
                "secondaryUrl":"http://",
                "nickname":"Tistory API",
                "title":"나만의 앱, Tistory OAuth API 로 만들어보세요!",
                "description":"",
                "default":"Y",
                "blogIconUrl":"http://i1.daumcdn.net/cfs.tistory/blog/79/795307/index.gif",
                "faviconUrl":"http://i1.daumcdn.net/cfs.tistory/blog/79/795307/index.ico",
                "profileThumbnailImageUrl":"http://cfile1.uf.tistory.com/R106x0/1851DB584DAF942950AF29",
                "profileImageUrl":"http://cfile1.uf.tistory.com/R106x0/1851DB584DAF942950AF29",
                "statistics":{
                    "post":"3",
                    "comment":"0",
                    "trackback":"0",
                    "guestbook":"0",
                    "invitation":"0"
                }
            },
            {
                "url":"http://oauth2.tistory.com",
                "secondaryUrl":"http://",
                "nickname":"Tistory API",
                "title":"나만의 비밀 홈",
                "description":"",
                "default":"N",
                "blogIconUrl":"http://i1.daumcdn.net/cfs.tistory/blog/79/795308/index.gif",
                "faviconUrl":"http://i1.daumcdn.net/cfs.tistory/blog/79/795308/index.ico",
                "profileThumbnailImageUrl":"",
                "profileImageUrl":"",
                "blogId":"795308",
                "statistics":{
                    "post":"0",
                    "comment":"0",
                    "trackback":"0",
                    "guestbook":"0",
                    "invitation":"0"
                }
            }
        ]
    }
}
```