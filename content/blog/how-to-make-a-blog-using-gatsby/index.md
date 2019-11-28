---
title: Gatsby로 블로그 만들기
date: '2019-11-28'
description: 간단하게 Gatsby를 이용해서 자신만의 블로그를 만들어 보자!
---

## 일단 Nodes.js 설치하자

[Node.js](https://nodejs.org/ko/) LTS 다운로드

## gatsby-cli 설치

**터미널** 환경에서

```Shell
npm install -g gatsby-cli
```

## 시작하기

gatsby new [[원하는 블로그 이름]] [[원하는 스타터 패키지(테마)]]

```Shell
ex) gatsby new my_blog https://github.com/gatsbyjs/gatsby-starter-blog
```

## 로컬 개발 환경 실행하기

```Shell
cd [[블로그 이름]] && gatsby develop
```

브라우저에서 [http://localhost:8000](http://localhost:8000) 접속 후  
자신의 입맛대로 블로그를 꾸며보자. (스타터 패키지에 따라 코드 및 테마가 다름)

## 일단 github.io repo를 만들자.

1. [https://github.com](https://github.com) 접속 및 로그인
2. 오른쪽 상단 +버튼 클릭, New Repository
3. Repository name에 [[사용자_이름]].github.io 입력
4. Public으로 만든다.

## Github remote 연결

```Shell
git remote origin add https://github.com/[[사용자 이름]]/[[사용자 이름]].github.io.git
```

## Github page로 배포하기

**gh-pages 모듈 설치**

```Shell
npm install --save-dev gh-pages
```

**package.json에 배포 스크립트 작성**

```JSON
{
  "scripts": {
    "deploy": "gatsby build && gh-pages -d public -b master"
  }
}
```

## 개발, 배포 브랜치 나누기 및 배포하기

본인: `master`(배포), `dev`(개발)

dev에서 개발하고 master에 merge한 뒤,  
master에서 `npm run deploy` 명령어를 통해 배포하고 있습니다.

## 사용하기

`https://[[사용자 이름]].github.io`로 접속
