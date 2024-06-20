### 사용한 자료구조 및 알고리즘
Stack, DFS

### 문제를 푸는데 걸린 시간
2n분 + 8분

### 나의 풀이

```Javascript
function solution(s) {
    if (s.length % 2 !== 0) return false;

    const s_stack = []; 
    s_stack.push({ index: 0, openbracket: 0, closebracket: 0 });

    while (s_stack.length > 0) {
        const { index, openbracket, closebracket } = s_stack.pop(); 

        if (index === s.length) {
            if (openbracket === closebracket) {
                return true;
            } else {
                continue;
            }
        }

        const itinerate = s[index];

        if (itinerate === '(') {
            s_stack.push({ index: index + 1, openbracket: openbracket + 1, closebracket: closebracket });
        } else if (itinerate === ')') {
            if (openbracket > closebracket) {
                s_stack.push({ index: index + 1, openbracket: openbracket, closebracket: closebracket + 1 });
            } else {
                return false;
            }
        }
    }

    return false;
}
```
괄호의 수가 짝수인지 홀수인지 확인
1. 사용자로부터 문자열을 입력받는다.
2. 문자열의 길이가 홀수인 경우 바로 false 반환. 짝수인 경우 코드를 계속 실행한다. 
- 
괄호의 짝이 맞는지 검사하기 위해서
1. DFS를 사용하여 초기 상태 `{ index: 0, openbracket: 0, closebracket: 0 }`를 스택에 추가한다.
2. 스택이 완전히 빌때까지 상태를 꺼내어 처리하고, 새로운 상태를 스택에 추가한다
   - index가 문자열 길이와 같고, 열린 괄호와 닫힌 괄호 수가 같으면 true를 반환한다.<br>
   - 여는 괄호 `(`이면 열린 괄호 수를 증가시키고 스택에 추가한다.<br>
   - 닫힌 괄호 `)`이면 열린 괄호 수가 더 많을 때만 스택에 추가한다.<br>
3. 모든 상태를 탐색해도 유효한 괄호 문자열을 찾지 못하면 `false`를 반환한다.


## 문제풀이 핵심개념
Stack, DFS를 이용한 유효성 검사

## 소감
평소에 DFS알고리즘이나 BFS알고리즘이나 대체로 결과값은 똑같이 나온다는 무지한 생각을 가지고 살며 대충 스텍+BFS, 큐+BFS를 이용한 풀이로 이 문제에 접근했더니 정확성 테스트는 통과했지만 효율성 테스트에서 계속 미끄러졌다. 문제풀이를 포기하려다 문득 DFS알고리즘을 사용해서 이 문제를 풀면 메모리 사용량이 줄어서 괜찮지 않을까 생각이 들어 써봤더니 맞았다..............
알고리즘 공부를 더 해야겠다...


### 다른사람의 풀이

```Javascript
function is_pair(s) {
    var result = s.match(/(\(|\))/g);
    return result[0] == '(' && result.length % 2 == 0 ? true : false;
}
```
정규표현식을 이용한 코드


## 잡소리
아무리 생각해도 많은 사람들에게 내 풀이를 공개하는 것은 좀 부끄럽다. 프로그래머스 탈주 고민중

