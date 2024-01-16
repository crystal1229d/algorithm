# [Lv.0] A 강조하기 
* #### [Link](https://school.programmers.co.kr/learn/courses/30/lessons/181874)
* #### Category : 
* #### Difficulty : 1 / 10  
* #### Solved : 1

<hr />

```js
function solution(myString) {
    return [...myString].map(str => {
        if (str === 'a') {
            return 'A';
        } else if (str === 'A') {
            return str;
        } else {
            return str.toLowerCase();
        }
    }).join('')
}
```

<br />

* How to solve
1. 1차풀이 : 테스트케이스 3 실패 ㅌ
```js
function solution(myString) {
    return [...myString].map(str => str === 'a' ? 'A' : str.toLowerCase()).join('')
}
```

2. 2차풀이=최종결과 : 성공 
* "A"가 아닌 모든 대문자 알파벳은 소문자 알파벳으로 변환

<br />

* another way
```js
const solution=s=>s.toLowerCase().replaceAll('a','A');
```
```js
function solution(myString) {
    return [...myString].map(str => ['a', 'A'].includes(str)? 'A' : str.toLowerCase()).join('');
}
```
```js
function solution(myString) {
    var answer = '';
    return [...myString].map(e => e == 'a' || e == "A" ? "A" : e.toLowerCase()).join("");
}
```