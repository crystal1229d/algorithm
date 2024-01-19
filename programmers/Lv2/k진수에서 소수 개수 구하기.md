# [Lv.2] [1차] k진수에서 소수 개수 구하기
* #### [Link](https://school.programmers.co.kr/learn/courses/30/lessons/92335)
* #### Category : 
* #### Difficulty : 4 / 10  
* #### Solved : 1

<hr />

```js
function solution(n, k) {
    const nums = n
        .toString(k)
        .split('0')
        .map(str => str*1)
        .filter(n => n >= 2)
        .filter(n => isPrime(n));
    
    return nums.length;
    
    function isPrime (n) {
        for (let i=2; i<=Math.floor(Math.sqrt(n)); i++) {
            if (n % i === 0) return false;
        }
        return true;
    }
}
```

<br />

* How to solve
1. 1차풀이 : 테스트케이스 14, 16 실패 
```js
function solution(n, k) {
    const nums = n
        .toString(k)
        .split('0')
        .map(str => str*1)
        .filter(n => n >= 2)
        .filter(n => isPrime(n));
    
    return nums.length;
    
    function isPrime (n) {
        for (let i=2; i<Math.floor(Math.sqrt(n)); i++) {
            if (n % i === 0) return false;
        }
        return true;
    }
}
```

2. 2차풀이=최종결과 : 성공 
* 소수판별 함수에서 `Math.floor(Math.sqrt(n))` 까지 검사해야하는데 등호를 빠트렸다..

<br />

* another way
```js
function isPrime(num){
    if(!num || num===1) return false;
    for(let i=2; i<=+Math.sqrt(num); i++){
        if(num%i===0) return false;
    }
    return true;
}

function solution(n, k) {    
    const candidates = n.toString(k).split('0');
    return candidates.filter(v=>isPrime(+v)).length;
}
```