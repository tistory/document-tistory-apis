# 파일 첨부 API

```
POST https://www.tistory.com/apis/post/attach?
  access_token={access-token}
  &blogName={blog-name}

[uploadedfile]
```

기본 매개변수를 제외한 매개변수는 다음과 같습니다.

- blogName: Blog Name 입니다.
- uploadedfile: 업로드할 파일 (multipart/form-data)

## 응답

- url: 업로드한 파일의 url
- replacer: 업로드한 파일의 치환자

## 응답 예

```
{
  "tistory":{
    "status":"200",
    "url":"http://cfile6.uf.tistory.com/image/1328CE504DB79F5932B13F",
    "replacer":"%5b%23%23_1N%7ccfile6.uf%401328CE504DB79F5932B13F%7cwidth%3d\"500\"+height%3d\"300\"%7c_%23%23%5d"
  }
}
```
