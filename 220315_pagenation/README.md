## 순수 JS로 비동기 Pagenation 구현해보기 (Jquery 사용 X)

1. public/board_list.js 에서 구현함

2. axios 라이브러리를 통해 back서버에서 DB 데이터를 당겨옴
   DB에서 게시판 데이터를 한꺼번에 다 가져와서 잘라서 쓰는 방식으로 진행

3. 미리 정하고 인지해야 하는 부분

- 전체 게시물 수
- 한 화면(한 페이지) 당 게시물 수  
  => 총 페이지 개수 = `Math.ceil(전체 게시물수/한 페이지 당 게시물 수)`

- 한 화면(한 페이지) 당 page index 개수  
  => 총 page index를 가진 block 개수 = `Math.ceil(총 페이지 개수/한 화면 당 page index 개수)`

4. key point

- **전역 변수냐 지역 변수냐**

  지역 변수로 설정해두었는데, 전역에서 쓰여야 할 경우, 전역에서 선언만 해주고,
  각 함수 내에서 값을 할당해주는 식으로 진행함

- **HTML `<template>` 엘리먼트 사용**

  페이지를 불러올 땐 화면상에 그려지지 않지만,  
  JS를 사용해서 내부에 필요한 데이터를 동적으로 넣어서 DOM요소에 추가해준다.  
  (대표적으로 replace 메소드 사용함)

  `.replace(교체할 텍스트, 새로 넣을 데이터)`
