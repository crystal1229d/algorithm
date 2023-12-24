# [Lv.0] 문자열 앞의 n글자 
* #### [Link](https://school.programmers.co.kr/learn/courses/30/lessons/181907)
* #### Category : 
* #### Difficulty : 0 / 10  
* #### Solved : 1

<hr />

```js
function solution(my_string, n) {
    // return [...my_string].slice(0, n).join('');
    return my_string.slice(0, n);
}
```

<br />

* another way
```js
function solution(my_string, n) {
   return my_string.slice(0, n)
}
```