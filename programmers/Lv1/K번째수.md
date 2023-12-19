# [Lv.1] K번째수
* #### [Link](https://school.programmers.co.kr/learn/courses/30/lessons/42748)
* #### Category : 
* #### Difficulty : 1 / 10  
* #### Solved : 1

<hr />

* `slice` 헷갈려 ㅠ.ㅠ
```js
function solution(array, commands) {
    return commands.reduce((acc, [i, j, k], idx) => {
        acc.push(array.slice(i-1, j).sort((a, b) => a - b)[k-1]);
        return acc;
    }, []);
}
```

<br />

* another way
```js
function solution(array, commands) {
    return commands.map(command => {
        const [sPosition, ePosition, position] = command
        const newArray = array
            .filter((value, fIndex) => fIndex >= sPosition - 1 && fIndex <= ePosition - 1)
            .sort((a,b) => a - b)    

        return newArray[position - 1]
    })
}
```