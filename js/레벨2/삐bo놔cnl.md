### 사용한 자료구조 및 알고리즘
DP

### 문제를 푸는데 걸린 시간
15분

### 나의 풀이

```Javascript
function solution(n) {
    var answer = [0, 1];

    for (var i = 2; i <= n; i++) {
         answer[i] = ( answer[i - 1] +  answer[i - 2]) % 1234567;
    }

    return  answer[n];
}
```
1. 매개변수 n을 입력받는 함수 solution 함수 solution. // 매개변수 n은 변수 answer 배열 마지막에 입력됨.
2. 함수 solution은 변수 answer를 가지고 있음. (배열 [0,1]) // 피보나치 수식 완성을 위해서 F(0) = 0,  F(1) = 1을 저장해야하기 때문에 초기화 해줄 필요가 있다.
3. 변수 answer는 2부터 n까지의 인덱스 요소를 순회하며 answer[i-1], answer[i-2] 의 합을 구하고, 이 값을 1234567로 나눠 answer[i]에 저장함.
4. 피보나치 수열에서 n번째 수 반환// cf. n = 10 이면, 결과 : 55 // 55는 1234567 보다 작아서 나누고 나머지를 구할 수 없다.

## 문제풀이 핵심개념
피보나치 수열은 무엇인가 , 중복되는 코드 작성이 필요없게 dp를 사용한 코드 최적화.

## 소감
학교수업을 예습해 보기위해 재귀적인 방법을 이용해 문제풀이를 하려했는데, 계속 시간 초과가 떠서 곤란했다. <br> 나중에 구글링 해보니 메모이제네이션 기법을 이용하면 재귀를 이용하면서도 시간초과가 뜨지 않게 할 수 있다고 한다.
```Javascript
/* 메모이제네이션 : 재귀 호출을 통해 피보나치 수열의 값을 계산한다.
// 이때,  memo라는 딕셔너리 자료형 변수에 계산값을 저장해두고 재귀 호출 전에 값을 먼저 확인하는 방식으로 불필요한 재귀호출을 줄이는 방식이다.
 출처 : https://stay-present.tistory.com/57*/

const solution = (n) => {
    const memo = [0, 1]; 
    
    for (let i = 2; i <= n; i++) {
        memo[i] = (memo[i - 1] + memo[i - 2]) % 1234567;
    }
    
    return memo[n];
};
```

### 다른사람의 풀이

```Javascript
function solution(num) {
  var count = 1; 
  var i = 0;
  var j = 1; 

  for(; count <= num ; count++){ 
    var temp = j; 
    j = i + j; 
    i = temp; 
  }
  return i; 
}
```
dp알고리즘을 이용한 코드<br>
1. 피보나치 수열의 첫 번째와 두 번째 값을 각각 i = 0, j = 1로 초기화
2. temp에 j 값을 저장
3. 주어진 num만큼 반복하여 피보나치 수열 계산 // 이 때, i값과 j 값 업데이트
4. 3에서 마지막으로 나온 i값 반환