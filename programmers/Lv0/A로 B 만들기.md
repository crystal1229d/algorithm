# [Lv.0] A로 B 만들기 
* #### [Link](https://school.programmers.co.kr/learn/courses/30/lessons/120886)
* #### Category : 수학, 시뮬레이션, 문자열, 조건문, 반복문
* #### Difficulty : 2 / 10  
* #### Solved : 1

<hr />

```js
function solution(before, after) {
    let before_asc = [...before].sort();
    let after_asc = [...after].sort();
    
    return JSON.stringify(before_asc) === JSON.stringify(after_asc) ? 1 : 0
}
```

<br />

* another way 
```js
function solution(before, after) {
    return before.split('').sort().join('') === after.split('').sort().join('') ? 1 : 0;
}
```