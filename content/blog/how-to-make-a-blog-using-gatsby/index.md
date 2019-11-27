---
title: Gatsby로 블로그 만들기
date: '2019-11-28'
description: overreacted 블로그 따라 만들고 싶죠?
---

## 일단 설치하자

Node.js

## gatsby-cli 설치

터미널 환경에서

npm install -g gatsby-cli 또는
yarn global add gatsby-cli

## gatsby 시작하기

gatsby new [[블로그\_이름]] [[원하는 스타터 패키지(테마)]]

ex) gatsby new blog https://github.com/gatsbyjs/gatsby-starter-blog

## 로컬 개발 환경 실행하기

cd [[블로그_이름]] && gatsby develop

브라우저에서 [http://localhost:8000](http://localhost:8000) 접속

## 일단 github.io repo를 만들자.

1. https://github.com 접속 및 로그인
2. 오른쪽 상단 + 버튼 클릭, New Repository
3. Repository name에 [[사용자_이름]].github.io 입력
4. Public으로 만든다. (Private X)
5. 방금 만든 레포의 Settings로 들어간다.

## Github page로 배포하기

npm install --save-dev gh-pages 또는
yarn add gh-pages --dev
