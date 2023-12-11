# [Lv.2] JadenCase 문자열 만들기
* #### Category : 
* #### Difficulty : 1 / 10  
* #### Solved : 1

<hr />

```js
function solution(s) {
    return [...s].map((str, idx) => {
        if (s[idx-1] === ' ' || idx === 0) {
            str = str.toUpperCase();
        } else {
            str = str.toLowerCase();
        }
        return str;
    }).join('');
}
```

<br />

* How to solve
* 처음에는 다른 방식으로 풀이해나가려고 했다. 
1. `split(' ')` 으로 띄어쓰기를 기준으로 문자열을 나눈다음 
2. 해당 배열의 0번째 문자만 UpperCase 로 변환하고 
3. `join(' ')` 으로 붙이려고 했다. 
* 그런데 실수로 3번 과정을 계속 `join('')` 으로 시도하다가 안된다고 착각해서 다른 방식으로 풀이했다...
* 다 풀고 다른사람 풀이를 보니 내 원래 생각대로 풀이한 분들이 많이 계셨고, 그 방법이 더 좋다고 느껴졌다. 

<br />

* another way 
```js
function solution(s) {
    return s.split(" ").map(v => v.charAt(0).toUpperCase() + v.substring(1).toLowerCase()).join(" ");
}
```