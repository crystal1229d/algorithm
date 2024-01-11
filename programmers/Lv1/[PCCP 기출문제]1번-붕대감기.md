# [Lv.1] [PCCP 기출문제] 1번 / 붕대 감기
* #### [Link](https://school.programmers.co.kr/learn/courses/30/lessons/250137)
* #### Category : 
* #### Difficulty : 2 / 10  
* #### Solved : 1

<hr />

```js
function solution(bandage, health, attacks) {
    const [castTime, hps, bonus] = bandage;
    const maxHealth = health;
    
    for (let i=0; i<attacks.length; i++) {
        const [time, damage] = attacks[i];
        if (i > 0) {
            const healDuration = time - attacks[i-1][0] - 1;
            const healBySec = hps * healDuration;
            const bonusHeal = Math.floor(healDuration / castTime) * bonus;
            health = health + healBySec + bonusHeal;
            if (health > maxHealth) health = maxHealth; // 최대체력 초과 시
        }   
        health -= damage;
        
        if (health <= 0) return -1;
    }
    
    return health;
}
```

<br />

* another way
```js
function solution(bandage, health, attacks) {
  let currHealth = health;
  let currTime = 0;

  for (let [attackTime, damage] of attacks) {
    let diffTime = attackTime - currTime - 1;
    currHealth += diffTime * bandage[1] + Math.floor(diffTime / bandage[0]) * bandage[2];

    if (currHealth > health) currHealth = health;
    currHealth -= damage;
    if (currHealth <= 0) return -1;
    currTime = attackTime;
  }

  return currHealth;
}
```