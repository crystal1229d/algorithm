# [Lv.0] qr code 
* #### [Link](https://school.programmers.co.kr/learn/courses/30/lessons/181903)
* #### Category : 
* #### Difficulty : 1 / 10  
* #### Solved : 1

<hr />

```js
function solution(q, r, code) {
    return [...code].filter((_, idx) => idx % q === r).join('')
}
```