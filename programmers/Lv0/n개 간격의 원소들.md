# [Lv.0] n개 간격의 원소들 
* #### [Link](https://school.programmers.co.kr/learn/courses/30/lessons/181888)
* #### Category : 
* #### Difficulty : 0 / 10  
* #### Solved : 1

<hr />

```js
function solution(num_list, n) {
    return num_list.filter((_, idx) => idx % n === 0);
}
```