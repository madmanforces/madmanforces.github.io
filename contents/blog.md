---
date: '2022-03-10'
title: 'gatsby로 블로그 & 포트폴리오 만들기 '
categories: ['Portfolio']
summary: 'React,Gatsby,GraphQL,'
thumbnail: './blog.png'
---

### 1. 소개

개발자라면 t-story나 네이버 블로그도 좋지만 자기가 만든 간단한 블로그 하나 정돈 있어야 하지 않을까!
그리고 기존에 있던 포트폴리오용 웹페이지가 너무 조잡하다 라고 생각되어 포트폴리오와 여러 지식들을 같이 보관할
블로그를 만들어보고 싶어서 만들게 된 프로젝트 입니다.

이 블로그는 기본적으로 메인 페이지와 게시글 페이지로 나누어져 있습니다.
메인페이지에선 저를 소개하는 문장과 프로필 사진이 있고
카테고리 별로 분류 해놓은 게시글들을 볼 수 있습니다.

게시글 페이지는 글을 쓸 수 있는 곳인데 일반적인 tsx파일에 글을 쓰는게 아닌
마크다운에 스크립트에 글을 쓰면 gatsby에서 html 태그로 변환되어
문자열 형태로 저장되는 식으로 만들었습니다.

먼저 마크다운 처리를 위해 필요한 라이브러리들을 설치 하고 gatsby.config.js에 플러그인 부분에 추가 해줍니다.
그리고 html 속성을 쿼리하고 쿼리한 html 속성에 마크다운 문법으로 작성하면 html 태그로 변환되는데
(dangerouslySetInnerHTML) 속성을 통해 html 코드를 출력합니다.
스타일은 해당 tsx 스크립트에 지정 해줍니다.

사용자 경험을 위해 404 페이지도 만들었고 크롬 앱을 통해 웹 접근성을 검사하고
몇 몇 태그들을 Footer Main 과 같은 Semantic Tag를 사용 했습니다.

또 지속적인 블로그로 쓸 계획이기 때문에 github와 연동하여 수정시 배포를 통해
바로 업데이트 할 수 있도록 gh-pages 라이브러리를 설치하여 관리 하고 있습니다.

### 2. WHY Gatsby?

기술 블로그 개발에 가장 잘맞는 프레임워크가 Gatsby라고 생각되어 Gatsby로 진행을 하였습니다. 왜냐하면
Gatsby는 정적 사이트 생성의 기능을 갖고있고 무엇보다 React 기반의 프레임워크이기 때문입니다.
그렇다면 같은 React 기반의 정적 사이트 생성의 기능을 가졌고 Gatsby보다 더 인기가 많은 Next.js를
사용하지 않은 이유가 무엇이냐?!
Next.js는 주로 서버사이드 렌더링을 위해 사용하는 프레임워크이기 때문입니다.

### 3. 느낀점

Gatsby 라는 프레임워크가 아무리 react 기반의 프레임워크라 해도 강의도 별로 없고 배울 수 있는 곳이 별로 없어서
걱정을 한 가득 안고 시작했는데 구글링을 통해 주먹구구 식으로 해결하면서 힘들긴 했지만 개발을 하면서 배울수 있는
기술이 꽤나 많았던것 같아서 좋았다. FE개발자를 준비하는 과정에서 GraphQL을 다뤄보기란 쉽지 않다고 생각 하는데,
Gatsby에선 빌드 타임에 있는 데이터를 가져다 쓸 때 GraphQL을 사용하기 때문에 사용하기 싫었어도(?!) 사용해야 했다.
예를 들면, 파일 시스템에서 어떤 JSON 파일을 읽어 와서 데이터 풀에 저장한 다음 파일명 등으로 쿼리하여
그 데이터를 페이지에 담아내는 식인데 설명은 복잡하지만 깊은 이해를 요구하는 것 같진 않았다.
검색이나 번역,등 데이터 조작을 필요로한다면 GraphQL사용이 복잡해진다고 하지만 이번 프로젝트에선 starter들이 쿼리를
전부 구현 해놓았기 때문에 frontmatter, slug 정도만 추가해서 사용했다.

그리고 Gatsby를 사용하면서 느낀점은 플러그인들의 역할이 아주 크다는 점이다. 데이터를 끌어모으거나
정적 웹사이트를 만들때 고려해야 하는 여러가지 일들을 플러그인이 알아서 해결해 준다. 여러 플러그인을 사용해야 하지만
그만큼 편하게 개발할수 있다. (gatsby.config.js 파일에서 플러그인 이름과 옵션만 줄줄이 이어붙이면 적용이 끝난다!)

추가적으로 블로그를 완성하고 나니 누군가가 나의 게시물을 보고 댓글을 달고 싶을 수 있으니 댓글 기능을 추가해 봐야겠다.
서버를 붙히지 않고 댓글 기능을 만들 방법을 찾아서 구현해 봐야겠다.

---

## Source

- 깃허브 링크

  [<https://github.com/madmanforces/madmanforces.github.io>](https://github.com/madmanforces/madmanforces.github.io)
