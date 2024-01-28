---
title: "[일기]get, setattr, getattr"
date: 2024-01-28
---

# 1. 작성 동기
1. 뭐라도 적어야 할 거 같아서 최근에 알게 된 것을 정리한다. 

# 2. 내용
1. get
    - get은 수업시간에 어떤 값을 가져올 때 쓰거나 딕셔너리에 키 조회시 예외처리로 활용이 가능했다.
    - 코드 예시가 기억이 나지 않아, chatgpt에 물어봤더니, request와 같이 쓰는 예시만 주로 보여주었다.
2. setattr
    - 간혹 반복문으로 나온 결과를 바로 이름이 갱신되는 변수로 넣고싶은 경우가 생긴다.
    - 이럴 떄는 mod = sys.modules[__name__] 을 활용해 반복문에서 매번 새로운 변수 이름을 생성할 수 있다.
    - 예를 들어 var1 = '내용 1', var2 = '내용 2', var3 = '내용 3' 이런 식으로 만드는 것이다.
3. getattr
    - 생성한 변수를 불러와서 활용하는 함수다. 


# 3. 참고
1. https://100.pyalgo.co.kr/?page=12#
2. https://medium.com/@unfinishedgod/동적으로-변수-생성-하기-r-python-7c1d8dbc56e3
3. https://data-newbie.tistory.com/353