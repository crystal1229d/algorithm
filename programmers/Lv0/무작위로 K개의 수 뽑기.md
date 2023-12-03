# [Lv.0] 무작위로 K개의 수 뽑기
* #### [Link](https://school.programmers.co.kr/learn/courses/30/lessons/181858)
* #### Category : 
* #### Difficulty : 4 / 10  
* #### Solved : 1

<hr />

```js
function solution (arr, k) {
	return [...new Set(arr), ...Array(k).fill(-1)].slice(0, k);
}
```

<br />

* #### How to solve
1. 1차풀이 : 성공
    1. 중복제거를 위해 Set 사용
    2. Set 에 수를 담음
    3. Set 의 length 가 k 보다 작은 경우, 남은 길이만큼 -1 로 채움
    4. Set 을 배열로 변환 (spread operator)
```js
function solution(arr, k) {
    let answer = new Set();
    
    arr.forEach(num => answer.add(num));
    answer = [...answer].slice(0, k);
    
    if (answer.length < k) {
        let rest = Array((k - answer.length)).fill(-1);
        answer = [...answer, ...rest]
    }
    
    return answer;
}
```

2. 2차풀이 = 최종결과 : 성공
* 1차풀이를 깨끗이 정리 
    1. 1~2, 4 -> ```[...new Set(arr)]
    2. 3 -> 굳이 length 검사하지 않고 일단 길이가 k 인 -1 로 채운 배열을 뒤에 붙인다음 마지막에 전체배열을 0부터 k 만큼 자르면 됨


<br />

* another way  
```js
function solution(arr, k) {
  const set = new Set(arr);
  return set.size < k ? [...set, ...Array(k - set.size).fill(-1)] : [...set].slice(0, k);
}
```
```js
function solution(arr, k) {
    return [...Array.from(new Set(arr)), ...new Array(k).fill(-1)].slice(0,k);
}
```
```js
const solution = (arr, k) => {
    const set = new Set(arr);
    const result = [...set].slice(0,k);
    while(result.length !== k){
        result.push(-1);
    }
    return result;
}
```
