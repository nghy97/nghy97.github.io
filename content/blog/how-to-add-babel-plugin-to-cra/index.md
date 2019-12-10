---
title: CRA에 Babel Plugin 추가하기
date: '2019-12-10'
description: create-react-app에서 eject하지 않고 플러그인 추가할 수 있을까?
---

### cra 설치

```Shell
npm install -g create-react-app
```

### 테스트 프로젝트 만들기

```Shell
create-react-app test && cd test
```

### react-app-rewired, customize-cra 설치

**test** 폴더 안에서

```Shell
npm install --save-dev react-app-rewired customize-cra
```

### @babel/plugin-proposal-optional-chaining 설치

```Shell
npm install --save-dev @babel/plugin-proposal-optional-chaining
```

test 디렉토리 안의 package.json에서 해당 부분을 수정한다.
```JSON
"scripts": {
  "start": "react-app-rewired start",
  "build": "react-app-rewired build"
}
```

브라우저에서 [http://localhost:8000](http://localhost:8000) 접속 후  
자신의 입맛대로 블로그를 꾸며보자. (스타터 패키지에 따라 코드 및 테마가 다름)

### 일단 github.io repo를 만들자.

1. [https://github.com](https://github.com) 접속 및 로그인
2. 오른쪽 상단 +버튼 클릭, New Repository
3. Repository name에 [[사용자_이름]].github.io 입력
4. Public으로 만든다.

### Github remote 연결

```Shell
git remote origin add https://github.com/[[사용자 이름]]/[[사용자 이름]].github.io.git
```

### Github page로 배포하기

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

### 개발, 배포 브랜치 나누기 및 배포하기

**본인**: `master`(배포), `dev`(개발, 본인이 원하는 이름 아무 거나 하셔도 됩니다 ,, 제 지인은 source로 하더라구요.)

dev에서 개발하고 master에 merge한 뒤,  
master에서 `npm run deploy` 명령어를 통해 배포하고 있습니다.

### 사용하기

`https://[[사용자 이름]].github.io`로 접속
