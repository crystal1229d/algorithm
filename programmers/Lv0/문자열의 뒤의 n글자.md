# [Lv.0] 문자열의 뒤의 n글자
* #### [Link](https://school.programmers.co.kr/learn/courses/30/lessons/181950)
* #### Category : 
* #### Difficulty : 0 / 10  
* #### Solved : 1

<hr />

```js
function solution(my_string, n) {
    return my_string.slice(-n);
}
```

<br />

* another way
```js
function solution(my_string, n) {
    return my_string.substring(my_string.length - n);
}
```