### 사용한 자료구조 및 알고리즘
구현

### 문제를 푸는데 걸린 시간
1분 미만

### 나의 풀이

```Javascript
function solution(num1, num2) {
    var numdiv = (num1 / num2) * 1000 
    var answer = Math.floor(numdiv)
    return answer
}

```
1. num2를 num1로 나눈뒤 1000을 곱한다.
2. floor 로 소숫점을 내림한다.

## 문제풀이 핵심개념
floor

## 소감
유익했다.

### 다른사람의 풀이

```Javascript
function solution(num1, num2) {
    return Math.trunc(num1 / num2 * 1000);
}

```

trunc 메서드를 활용해 소수점 이하를 버린다.<br>
사용자가 음수를 입력했을때 <br>
```Javascript
Math.floor(23.3) = 23
Math.floor(-23.3) = -24
```
이런식의 결과가 출력될 수도 있기때문에 trunc 메서드를 선택해서 사용하는게 더 좋았다.