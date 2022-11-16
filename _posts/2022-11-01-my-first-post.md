---
layout: post
title: "첫 블로그 포스팅"
author: "forlivd"
categories: til
tags: [android, sample]
image: start-up_picpedia_CCBYSA.PNG
---
###### [Nick Youngson](https://www.picpedia.org/chalkboard/s/start-up.html)/[CC BY-SA](https://creativecommons.org/licenses/by-sa/3.0/)


   <br/>

## 축! 블로그 첫 포스팅!

   <br/>

### [22.11.16 TIL]

   <br/>

1. **블로그 세팅을 더 진행하였다.**

   setting에서 홈에 보여줄 카테고리들과 링크를 설정하고,
   pages에 카테고리를 만들어 주었다.

   post에 게시글을 작성할 때 categories를 작성해주면 해당 카테고리로 보인다.

   _todo : email 등 contact 작성 및 연결, ReadME 수정, about 작성_

   필요 없는 아이콘 및 항목 지우기(상단 컨텍트), 댓글과 상세 페이지(가능?) 구현

   <br/>

2. **Feed 조회 구현**

   서버에서 페이징 된 데이터를 받아와 Paging3로 안드로이드에서 띄워주었다.

   LiveData를 쓸 때와는 다른 점이 많다. (클린 아키텍쳐의 적용도 한몫했지만..)
   cachedIn 된 flow 데이터를 Fragment에서 관찰하게 한다.

   _todo : 클린 아키텍쳐에서는 어느 위치에서 chchedIn된 데이터를 생성해야 할지 좀 더 고민이 필요하다._

   paging adapter 데이터를 갱신하는 것은 paging datasource의 refresh를 구현하고,
   adapter.refresh()를 하면 된다.

      <br/>

3. **서버 통신 오류**

   400 대 오류는 연결 자체가 문제가 있을 경우 자주 봤는데, 415는 처음 봤다.

   Add Feed를 성공해도 서버에서 그 이후의 작업을 처리하는 중 에러가 나면
   http error가 발생한다.

   add가 안된 줄 알고 수정하고자 했는데, 알고 보니 그 이후의 통계 처리 로직에서 에러가 났다.

   그래서 실제로 DB에는 add가 되었지만 반환은 error가 왔다.

   _todo : 나중에 서버 담당자와 한 번 할 수 있는 모든 방식으로 에러를 발생시켜 보기로 했다._

---

블로그 작성 연습용으로 간단히 작성.
TIL은 내가 공부한 내용을 일기처럼 적으니 블로그 포스팅만큼 부담스럽진 않은 듯.
이건 자주 쓸 수 있을 것 같다.

_todo : 해당 연습 페이지 삭제 또는 수정, todo 같은 거 모아 볼 수 있게 하는 기능 찾아보기, lastmodified 입력 가능하게 하기, 좌우에 정보 띄우기_

<!-- excerpt: "블로그를 개설하였다! 재밌다. ㅎㅎ"

toc: false
toc_sticky: false

date: 2022-11-01
last_modified_at: 2022-11-01 -->
