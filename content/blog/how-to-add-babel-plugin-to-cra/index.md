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

### config-overrides.js 파일 생성

```JavaScript
const { useBabelRc, override } = require('customize-cra');
module.exports = override(useBabelRc());
```

### .babelrc.js 파일 생성

```JavaScript
module.exports = {
  plugins: ['@babel/plugin-proposal-optional-chaining'],
};
```

### package.json 수정

```JSON
"scripts": {
  "start": "react-app-rewired start",
  "build": "react-app-rewired build"
}
```

### VS Code 경고 제거

`.vscode/settings.json` 파일 생성 후

```JSON
{
  "javascript.validate.enable": false
}
```
