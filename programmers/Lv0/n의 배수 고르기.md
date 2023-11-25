# [Lv.0] n의 배수 고르기 
* #### [Link](https://school.programmers.co.kr/learn/courses/30/lessons/120905)
* #### Category : 문자열, 수학, 조건문, 배열, 사칙연산
* #### Difficulty : 1 / 10  
* #### Solved : 1

<hr />

```js
function solution(n, numlist) {
    return numlist.filter((num) => num % n === 0)
}
```