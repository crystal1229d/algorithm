# [Lv.1] x만큼 간격이 있는 n개의 숫자 
* #### [Link](https://school.programmers.co.kr/learn/courses/30/lessons/12954)
* #### Category : 
* #### Difficulty : 1 / 10  
* #### Solved : 1

<hr />

```js
function solution(x, n) {
    let answer= [x]
    for (let i=1; i<n; i++) {
        answer.push(x+x*i)
    }
    return answer
}
```

<br />

* another way
```js
function solution(x, n) {
    return Array(n).fill(x).map((v, i) => (i + 1) * v)
}
```