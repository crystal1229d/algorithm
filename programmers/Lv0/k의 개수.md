# [Lv.0] k의 개수 
* #### [Link](https://school.programmers.co.kr/learn/courses/30/lessons/120887)
* #### Category : 수학, 시뮬레이션, 문자열, 조건문, 반복문
* #### Difficulty : 2 / 10  
* #### Solved : 1

<hr />

* 풀긴했으나, 소요시간이 너무 길다 
```js
function solution(i, j, k) {
    let count = 0;
    
    for (let n=i; n<=j; n++) {
        let arr = [...n.toString()]
        for (let m=0; m<arr.length; m++) {
            if (k === arr[m]*1) {
                count++;
            }
        }
    }
    
    return count;
}
```

<br />

* another way 
```js
function solution(i, j, k) {
    let a ='';
    for(i;i<=j;i++){
        a += i;
    }

    return a.split(k).length-1;
}
```
```js
function solution(i, j, k) {
    let str = Array(j - i + 1).fill(i).map((v, i) => v + i).join('')
    return Array.from(str).filter(t => +t === k).length;
}
```
```js
function solution(i, j, k) {
    return Array(j-i+1).fill(i).map((v,i)=>v+i).join('').split(k).length-1;
}
```