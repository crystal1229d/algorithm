# [Lv.1] 문자열 내 p와 y의 개수 
* #### [Link](https://school.programmers.co.kr/learn/courses/30/lessons/12916)
* #### Category : 
* #### Difficulty : 1 / 10  
* #### Solved : 1

<hr />

```js
function solution(s){
    let count_p = 0;
    let count_y = 0;
    
    for (let i=0; i<s.length; i++) {
        if (s[i] === 'p' || s[i] === 'P') {
            count_p++;
        } else if (s[i] === 'y' || s[i] === 'Y') {
            count_y++;
        }
    }
    
    if (count_p === count_y) {
        return true;
    } else {
        return false;
    }
}
```

<br />

* another way
```js
function numPY(s){
    return s.toUpperCase().split("P").length === s.toUpperCase().split("Y").length;
}
```
```js
function numPY(s){
  return s.match(/p/ig).length == s.match(/y/ig).length
}
```
```js
function solution(s){
    return [...s.toLowerCase()].reduce((acc, cur) => {
        if(cur ==='p') return acc + 1;
        else if(cur ==='y') return acc - 1;
        return acc;
    }, 0) ? false : true;
}
```