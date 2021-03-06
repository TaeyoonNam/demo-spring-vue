# Spring Boot + Vue.js 데모 프로젝트

## 개발버전
- Spring Boot 2.5.5 / gradle 7.0 / npm 7.24.0 / node 14.5.0 / @vue cli 4.5.15 / mysql 5.7
- docker version 20.10.10 
- mysql docker hub (https://hub.docker.com/r/naming0617/mysql)

## 개발배경
- 관리자 페이지 개발을 위한 데모 프로젝트 스타트!
- 개발환경 셋팅 참고 (https://deockstory.tistory.com/26)  

## 참고내용
**1. npm은 무엇일까?**  
- "Node Package Manager"는 Node.js를 위한 기본 패키지 관리자로써, Java의 Gradle, PHP의 Composer과 같은 기능을 제공합니다.
- Webpack, Babel이란?
    - Webpack은 모듈 번들링을 통해 여러 JS파일들을 하나의 JS파일로 생성하는 것.
        - 왜 이러한 기능이 필요할까? 페이지 호출 시 여러 js 파일들을 불러오는데, 해당 파일들을 하나로 통합관리함으로써 네트워크 절약이 가능하다.
    - Babel은 새로운 버전의 JS 코드를 구 버전의 JS 코드로 변환시켜 주는 모듈.
        - 왜 이러한 기능이 필요할까? 각 브라우저별로 JS를 지원해주는 버전이 제각각이다. 따라서 개발자 입장으로써 최신 버전의 JS 코드를 사용 할 수 있지만, 컴파일 시 구버전으로 변환해줌으로써 확장성있는 서비스 개발이 가능하다.  

참고 (https://medium.com/front-end-weekly/what-are-npm-yarn-babel-and-webpack-and-how-to-properly-use-them-d835a758f987)  
  
**2. package.json에 있는 파일들은 무엇일까?**  
해당 파일은 npm 설치 시(npm init) 기본적으로 볼 수 있는 파일인데, 자바스크립트 패키지 범위와 정보를 알려주기 위한 파일입니다. 즉, maven, gradle과 같이 라이브러리나 모듈들을 관리하기위한 파일이라고 볼 수 있습니다. 또한 package-lock.json은 노드 패키지 간의 의존 관계를 고정시켜둔 파일입니다.
- scripts : 패키지의 라이프사이클 이벤트를 관리  
- dependencies : 일반적인 경우 의존하고 있는 것들을 작성.  
- devDependencies : 개발 모드에서만 의존하고 있는 목록. 실제로 배포할 때 필요없는 테스트 도구 등을 작성합니다.  

버전 표기는 [메이저].[마이너].[패치] 방식으로 되어있으며, 참고해야될 사항은 '^'는 마이너버전까지 변경허용. '~'는 패치버전까지 변경을 허용한다는 표현입니다. 예를 들어, ^1.3.2가 있으면 1.4.5는 허용하지만, 2.0.0은 허용하지 않고, ~1.3.2가 있으면 1.3.8까지는 허용하지만 1.4.0은 허용하지 않는다는 겁니다.  
  
**3. Vue.js는 무엇일까? React.js와 비교한 내용**  
 두 프레임워크 모두 컴포넌트(https://velog.io/@sms8377/Javascript-Vue-에서-컴포넌트란) 기반으로 이뤄졌고, Virtual DOM 방식이라는 점에 공통점이 있어서, 가볍고 빠르다는 평을 받고 있습니다.
 무엇이 더 좋고 나쁘다는 우열을 가리긴 어렵고, Vue는 HTML 템플릿 기반으로 이뤄져 있으며, React의 경우 JSX(자바스크립트 확장문법) 기반으로 이뤄져있어 개인적인 생각으로는 Vue가 상대적으로 배우기 쉬울거라고 생각됩니다.  
 - **컴포넌트란** 템플릿 화면에 구성요소를 조작 할 수 있는 블록을 의미하며, 컴포넌트를 활용할 경우 코드를 구조화 할 수 있고 일괄적인 패턴으로 개발 할 수 있다는 장점이 있습니다.  
 - **Virtual DOM**이란 가상의 DOM을 메모리에 올려두어 페이지 변경 시 전체 DOM을 새롭게 불러오는 것이 아니라 기존에 Virtual DOM에 존재한 형식을 비교해 변경된 부분만을 수정해줍니다.
   
- 참고  
 : React.js vs Vue.js, 자바스크립트 프레임워크 비교(https://library.gabia.com/contents/8284/)  
 : npm documents(https://docs.npmjs.com/cli/v7/using-npm/scripts)  
 : zerocho package.json(https://www.zerocho.com/category/NodeJS/post/5825a3caaff5c70018279975)  
 : zerocho 노드 프로젝트의 설정 파일들 (https://www.zerocho.com/category/NodeJS/post/5b934c8e6c974e001b710767_)
 : mysql docker 설정 : http://jmlim.github.io/docker/2019/07/30/docker-mysql-setup/