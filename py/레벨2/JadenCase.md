### 사용한 자료구조 및 알고리즘
구현

### 문제를 푸는데 걸린 시간
8분

### 나의 풀이

```Python

def solution(s):
    return ' '.join(s.capitalize() for s in s.split(' '))


```
1. 리스트 컴프리헨션으로 문자열 s를 리스트로 받는다. 
2. s는 공백('')을 기준으로 분리되어 리스트의 원소가 된다. 
3. 리스트의 원소는 모두 첫글자가 대문자로 바뀐다.(capitalize() 사용)
4. 공백을 기준으로 다시 합쳐져 반환된다.

## 문제풀이 핵심개념
내장함수 capitalize(), join


### 다른사람의 풀이

```Python
def Jaden_Case(s):
    return s.title()
```

내장메소드를 이용해 첫글자를 대문자로 바꾸어 반환하는 풀이.

