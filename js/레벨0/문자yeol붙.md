### 사용한 자료구조 및 알고리즘
구현

### 문제를 푸는데 걸린 시간
2분

### 나의 풀이

```Javascript
const readline = require('readline');
const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout
});

let input = [];

rl.on('line', function (line) {
    input = line.split(' ');
}).on('close', function () {
    str1 = input[0];
    str2 = input[1];

    let result = str1.concat(str2);

    console.log(result);
});
```
1. 문자열을 입력받는다. 이후 공백을 기준으로 str1과 str2를 나눈다.
2. concat으로 문자열을 이어 출력한다.

## 문제풀이 핵심개념
concat

## 소감
1개 이하, 2개 이상의 문자열을 입력받았을때 예외처리도 했었더라면 좋았을 것 같다.

### 다른사람의 풀이

```Javascript
const readline = require('readline');
const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout
}).on('line', function (line) {
    const strArr = line.split(' ')
    console.log(strArr.join(''))
})
```
1. 문자열을 입력받는다. 이때, 공백에 따라 단어를 구분한다.
2. join을 이용해 단어를 이어붙이고 출력한다.

