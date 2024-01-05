# [Lv.2] H-Index 
* #### [Link](https://school.programmers.co.kr/learn/courses/30/lessons/42747)
* #### Category : 
* #### Difficulty : 5 / 10  
* #### Solved : 0

<hr />

```js

```

<br />

* How to solve
1. 1차풀이 : 실패
```js
function solution(citations) {
    citations.sort((a, b) => a - b);
    let index = Math.floor(citations.length/2);
    
    while (index > 0 && index <= citations.length) {
        let citation = citations[index];
        let smaller = citations.slice(0, index+1).filter(n => (n <= citation)).length;
        let bigger = citations.slice(index).filter(n => (n >= citation)).length;
        
        if (smaller === bigger) {
            return citations[index];
        } else if (smaller > bigger) {
            index--;
        } else if (smaller < bigger) {
            index++;
        }
    }
    
    return citations.length;
}
```
