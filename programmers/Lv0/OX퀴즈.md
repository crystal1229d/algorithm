# [Lv.0] OX퀴즈 
* #### [Link](https://school.programmers.co.kr/learn/courses/30/lessons/120907)
* #### Category : 문자열, 수학, 조건문, 배열, 사칙연산
* #### Difficulty : 2 / 10  
* #### Solved : 1

<hr />

```js
function solution(quiz) {
    return quiz.map((q) => {
        let [formula, answer] = q.split('=')
        return eval(formula) === +answer ? 'O' : 'X' 
    })
}
```