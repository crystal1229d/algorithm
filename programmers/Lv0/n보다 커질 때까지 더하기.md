# [Lv.0] n보다 커질 때까지 더하기 
* #### [Link](https://school.programmers.co.kr/learn/courses/30/lessons/181884)
* #### Category : 
* #### Difficulty : 0 / 10  
* #### Solved : 1

<hr />

```js
function solution(numbers, n) {
    let sum = 0;
    for (let i=0; i<numbers.length; i++) {
        sum += numbers[i];
        if (sum > n) break;
    }
    return sum;
}
```

<br />

* another way
```js
function solution(numbers, n) {
    return numbers.reduce((a,c,i,t)=>(a<=n)?a+c:a)
}
```