# [Lv.2] N개의 최소공배수 
* #### [Link](https://school.programmers.co.kr/learn/courses/30/lessons/12953)
* #### Category : 
* #### Difficulty : 4 / 10  
* #### Solved : 1

<hr />

```js
function solution(arr) {
    // const gcd = (a, b) => a % b === 0 ? b : gcd(b, a % b);
    // const lcm = (a, b) => a * b / gcd(a, b);
    
    // GCD = 최대공약수
    // LCM = 최소공배수
    // 두 수 (a, b)의 최송공배수는 어떻게 구하는가?
    // a x b = GCD * LCM입니다.
    // LCM = a x b / GCD
    
    const gcd = (a, b) => a % b === 0 ? b : gcd(b, a % b);
    return arr.reduce((acc, num, _) => (acc * num) / gcd(acc, num), 1);
}
```

<br >

* How to solve 
* 최소공배수, 최대공약수 관해서 검색해서 다른 분들의 조언을 구해 겨우 풀었다.. 수학적인 내용이 나오면 너무 약해진다. 
* 유클리드 호제법 이용 

<br />

* another way
```js
function getGcd(a, b) {
  if (b === 0) return a;
  return getGcd(b, a % b);
}

function solution(arr) {
  return arr.reduce((a, b) => (a * b) / getGcd(a, b));
}
```
```js
function nlcm(num) {
 return num.reduce((a,b) => a*b / gcd(a,b))  
}

function gcd(a, b) {
  return a % b ? gcd(b, a%b) : b
}
```
```js
function solution(arr) {
    return arr.reduce((acc, cur) => {
        const recursive = (min, max) =>{
          return (min % max) === 0 ? max : recursive(max, min % max);
        }

        let max = 0;
        return acc*cur / recursive(acc,cur);
    });
}
```