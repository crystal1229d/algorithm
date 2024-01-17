# [Lv.2] 짝지어 제거하기 
* #### [Link](https://school.programmers.co.kr/learn/courses/30/lessons/12973)
* #### Category : 
* #### Difficulty : 5 / 10  
* #### Solved : 0

<hr />

```js
function solution(s)
{
    let stack = [];
    for (let i=0; i<s.length; i++) {
        if (stack[stack.length-1] === s[i]) {
            stack.pop();
        } else {
            stack.push(s[i]);
        }
    }
    return stack.length === 0 ? 1 : 0;
}
```

<br />

* How to solve
1. 1차풀이 : 효율성테스트2 실패 
```js
function solution(s)
{
    let stack = [];
    
    for (let i=0; i<s.length; i++) {
        if (stack[stack.length-1] === s[i]) {
            stack.pop();
        } else {
            stack.push(s[i]);
        }
    }
    
    return stack.length === 0 ? 1 : 0;
}
```

2. 2차풀이 = 1차풀이 = 최종풀이 
* 여기서 어떻게 더 효율을 따지면서 풀어내야할지 생각해내지못함.. 
* 다른날 1번 풀이 실행하니 통과. 왜 ?