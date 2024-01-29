---
title: "[일기]get, setattr, getattr"
date: 2024-01-28
---

# 1. 작성 동기
1. 뭐라도 적어야 할 거 같아서 최근에 기록해야할 것과 파이썬 책 집필을 위해 공부하다가 알게 된 것을 정리한다. 

# 2. 내용
1. get

    - get은 수업시간에 어떤 값을 가져올 때 쓰거나 딕셔너리에서 키를 조회하여 값을 가져오거나 키가 없다면 예외처리로 활용이 가능했다.

    - 딕셔너리의 키와 get을 통한 정렬

        ```python
        # 우편번호 정렬
        # https://100.pyalgo.co.kr/?page=12#
        # key값과 get을 통한 정렬
        data = [['제주시 A동 한라산길 61', '제주시 B동 백록담길 63', '제주시 C동 사라봉길 31'], 
        {'A동': 63007, 'B동': 63010, 'C동': 63002}]

        a, b = data
        # print(a) # ['제주시 A동 한라산길 61', '제주시 B동 백록담길 63', '제주시 C동 사라봉길 31']
        # print(b) # {'A동': 63007, 'B동': 63010, 'C동': 63002}
        ```

        ```python
        # step1 : a와 b의 공통사항이 동 이름이므로 동 이름을 이용해서 연결해보자.
        #         그렇다면 a에서 어떻게 추출하면 b의 키와 같은 값을 뽑을 수 있는지 확인해보자.

        for i in a:
            # print(i) # 제주시 A동 한라산길 61
            # print(i.split(' ')) # ['제주시', 'A동', '한라산길', '61']
            print(i.split(' ')[1]) # A동

        for i in b:
            print(i) # A동
        ```

        ```python
        # step 2 : 정렬대상은 a고 정렬 기준은 동이름의 키에 해당하는 값이다. 
        #          a에서 b의 키와 동일한 값을 추출할 수 있는 점 이용
        #          B의 키 a의 element.split(' ')[1]
        #          정렬대상 = a, 정렬 기준 = b.get(x.split(' ')[1]) # a의 element를 x라고 가정
        sorted(a, key = lambda x: b.get(x.split(' ')[1]))
        ```

    - get을 통한 예외처리

        ```python
        dic = {'a' : 1, 'b':2, 'c': 3}
        for i in dic:
            print(dic[i])
            print(dic.get(i))

        print(dic['d']) # error : KeyError: 'd'
        ```

        ```python
        print(dic.get('d')) # None
        print(dic.get('d', '존재하지 않는 키입니다.')) # 존재하지 않는 키입니다.
        ```

    - 별도로 chatgpt에 물어봤더니, request와 같이 쓰는 예시만 주로 보여주었다.


2. setattr
    - 간혹 반복문으로 나온 결과를 바로 이름이 갱신되는 변수로 넣고싶은 경우가 생긴다.
    - 이럴 떄는 mod = sys.modules[__name__] 을 활용해 반복문에서 매번 새로운 변수 이름을 생성할 수 있다.
    - 예를 들어 var1 = '내용 1', var2 = '내용 2', var3 = '내용 3' 이런 식으로 만드는 것이다.

        ```python
        import sys
        import random
        mod = sys.modules[__name__]
        for i in range(5):
            setattr(mod, f'var{i+1}', i+1)
        ```

3. getattr
    - 생성한 변수를 불러와서 활용하는 함수다. 
    
        ```python
        for i in range(5):
            print(getattr(mod, f'var{i+1}'))
        ```

# 3. 참고
1. https://100.pyalgo.co.kr/?page=12#
2. https://medium.com/@unfinishedgod/동적으로-변수-생성-하기-r-python-7c1d8dbc56e3
3. https://data-newbie.tistory.com/353
