# [Lv.0] 홀수 vs 짝수 
* #### [Link](hhttps://school.programmers.co.kr/learn/courses/30/lessons/181887)
* #### Category : 
* #### Difficulty : 0 / 10  
* #### Solved : 1

<hr />

```js
function solution(num_list) {
    let odd_sum = 0;
    let even_sum = 0;
    num_list.forEach((num, idx) => {
        // 첫 번째 idx = 1 이므로 짝수이면 홀수 취급, 홀추이면 짝수 취급 
        if (idx % 2 === 0) { odd_sum += num } 
        else { even_sum += num }
    })
    
    return odd_sum >= even_sum ? odd_sum : even_sum;
}
```

<br />

* another way
* 더 깔끔하게 작성 
```js
function solution(num_list) {
    let even = 0;
    let odd = 0

    num_list.map((v, idx) => {
        !(idx % 2) ? even += v : odd += v; 
    })

    return odd > even ? odd : even; 
}
```
```js
function solution(num_list) {
    let odd = 0;
    let even = 0;

    num_list.forEach((x,i) => i%2 == 0 ? even += x : odd += x);


    return Math.max(odd, even);
}
```