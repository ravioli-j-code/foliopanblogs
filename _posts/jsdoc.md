---
title: JSDoc
date : 2021-05-15
categories : ['javascript']
---

JSDoc 은 java에서 사용되는 javadoc과 마찬가지로 자바스크립트의 소스에 기술된 주석을 정리해주는 라이브러리입니다.  JSDoc 사이트(https://jsdoc.app/)에 들어가보면 지원되는 태그들이 정의되어 있습니다. Intellij 나 이클립스 등의 개발 플랫폼에서 해당 태그들을 템플릿으로 정리하여 주석을 작성하면 해당 내용을 문서화할 수 있습니다.

JSDoc 라이브러리를 사용하기 위해서는 npm이 설치되어 있어야 합니다. 

```
> npm init -y
```

![npm_init](/image/npm_init.png)

npm init을 실행하면 아래와 같이 package.json과 node_modules 폴더로 구성된 구조가 만들어집니다.

![npm_folder](/image/npm_folder.png)


```
> npm i -D jsdoc
```

위 명령어를 입력하여 아래와 같이 jsdoc을 설치합니다. 

![npm_install_jsdoc](/image/npm_install_jsdoc.png)


설치하면 아래와 같이 node_modules 폴더안에 jsdoc 모듈이 설치된 것이 보입니다. 설치 후에 바로 사용할수 있지만 템플릿을 적용하여 보기 편한 레이아웃으로 보기 위해 jsdoc을 위해 나온 템플릿을 설치해줍니다.

jsdoc에는 html 템플릿이 argon, minami, docdash 등 여러가지가 있는데 docdash 를 적용해보도록 하겠습니다.

argon

![argon](/image/argon.png)


minami ( https://github.com/interledger/jsdoc-template )
![minami](/image/minami.png)


docdash ( https://github.com/HalZhan/docdash-with-search ) 
![docdash](/image/docdash.png)


아래와 같이 docdash를 설치해줍니다.

```
> npm install docdash
```

![npm_install_docdash](/image/npm_install_docdash.png)


docdash 를 설치한 뒤 아래 같이 jsdoc 명령어가 잇는 경로(./node_modules/jsdoc) 에 jsdoc 명령어를 입력하고 타겟 폴더(C:\Users\kong\svnworks\wbetdev\src\main\resources\static\js\common) 를 지정한뒤 -t (템플릿 사용), -r ( recursive action ) 두 인자값을 추가해준 뒤 docdash 가 설치된 경로 ( C:\Users\kong\iCloudDrive\Documents\source\javascript\jsDoc\node_modules\docdash ) 를 지정해준뒤 실행합니다.

```
./node_modules/.bin/jsdoc C:\Users\kong\svnworks\wbetdev\src\main\resources\static\js\common -r -t C:\Users\kong\iCloudDrive\Documents\source\javascript\jsDoc\node_modules\docdash
```

![npm_install_docdash](/image/npm_install_docdash.png)

위 명령어를 터미널에서 실행하면 실행한 폴더 위치에 out 폴더가 생성되며 아래 구조로 html 파일들이 생성됩니다.

![out](/image/out.png)

index.html 파일을 실행하면 다음과 같이 docdash 템플릿이 적용된 jsdoc 파일이 보여집니다.

![result](/image/result.png)

브라우저에서 js파일들에 단 주석들이 함수별로 보여지는걸 볼수 있습니다. 태그를 잘 활용하면 프로젝트 내의 js파일 주석들로 유용한 javascript API 문서를 작성할 수 있습니다.
