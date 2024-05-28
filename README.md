# Netlify배포에 대한 문제점
<img width="827" alt="netlify에 배포한 사이트 보안오류" src="https://github.com/h0ri04/noona_Google_clone/assets/170905611/e47d9958-3ff8-49e5-b4e3-5f34bae66c0f">
</br>
해당 이미지와 같이 [netlify로 배포한 웹사이트](https://noonagoogleclone.netlify.app) 에 접속시 구글에서 웹사이트에 대한 보안이유로 연결을 차단하고 있습니다.


## Vercel배포에 대한 문제점
[vercel에 배포한 웹사이트](https://noona-google-clone.vercel.app/)또한 Netlify에서 배포한 사이트와 똑같이 오류가 발생하고 있습니다.

## 보안 문제에 대한 원인 분석
아직 무엇이 원인인지 잘 모르겠습니다.

1. form태그에 action속성에 실제 구글링이 가능하게 한 부분.

```html
 <form action="https://www.google.com/search" method="GET"">
          <fieldset>
            <legend class="sr-only">검색창</legend>
            <div class="search_wraper">
             ...
            <div class="btn_wrapper">
              <button type="submit" class="search_btn btn">Google 검색</button>
              <button class="lucky_btn btn">I'm Feeling Lucky</button>
            </div>
          </fieldset>
        </form>
```


하지만, 이 action코드를 제거해도 문제는 해결되지 않았다.

2. 너무 똑같이 클론코딩해서 구글 세이프 브라우징이 식별했다.

이 부분이 가장 문제와 가깝다고 생각한다. 어떤 방법으로 세이프 브라우징이 실행되는지는 모르겠지만, 구글링을 해본 결과 비슷한 문제에 직면한 글을 몇개 보았다.
[구글 세이프 브라우징 - 사기성 사이트(velog]('https://velog.io/@nu11/%EA%B5%AC%EA%B8%80-%EC%84%B8%EC%9D%B4%ED%94%84-%EB%B8%8C%EB%9D%BC%EC%9A%B0%EC%A7%95-%EC%86%8C%EC%85%9C-%EC%97%94%EC%A7%80%EB%8B%88%EC%96%B4%EB%A7%81-%EA%B3%B5%EA%B2%A9')


## 해결방법 
똑같이 만들지만, 일부 덜 만들거나 개성을 추가하면 될 수도 있을거같다. 하지만 클론코딩이라는 점에서 이대로 냅둬도 괜찮을 것 같다는 생각을 한다.

<img width="566" alt="스크린샷 2024-05-29 오전 1 18 25" src="https://github.com/h0ri04/noona_Google_clone/assets/170905611/332bd6cd-9a02-4e64-8cec-444824ddf5c2">

하지만 위와 같이 문구를 추가해봐도 해결되지 않는걸 봐서는 어느정도까지 고쳐야 하는지 잘 모르겠다. 이미 보안위협사이트로 등록되서 이미지를 바꿔도 계속해서 보안안내 문구가 등장하는건지...

