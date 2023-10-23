# 클린 코드 프론트엔드 | 프리온보딩 FE 챌린지 11월 (2023)

>https://www.wanted.co.kr/events/pre_challenge_fe_15

## 챌린지 과제

### Q1. 내가 생각하는 클린 코드란?

* 나만 이해하는 코드가 아닌 동료들이 **원활하게** 이해할 수 있는 코드.
* 유지보수에 품이 덜 들어가는 코드

### Q2. 내가 생각하는 (프론트엔드에서의) 클린 코드란?

* (FE단은 수정이 자주 일어나기 때문에) MVP(최소기능제품)를 지켜 간결하게 가져가는 코드라 생각한다.
* 변형하더라도, 로직을 빠르게 찾고 수정할 수 있게끔 하는 코드 (확장성 있는 코드).

### Q3. 내가 클린코드보다 중요하게 생각하는 것은?

* 동료와의 커뮤니케이션
* 문서화하기
* git convention


### Q4. 다음 중 선호하는 방식과 그 이유는?

##### 1. `Tab` vs `Space`

`Tab`을 선호한다. 간격은 신경쓰지 않고, 입력 횟수가 적기 때문.
팀의 규칙을 따라 tab의 간격을 정하는 편.

##### 2. `세미콜론 O` vs `세미콜론 X`

세미콜론을 붙이는 편이다. TS를 사용할 때도 붙인다.
하지만 팀의 규칙에 따라 바꿔도 상관 없다.

##### 3. `count++;` vs `count += 1;` vs `count = count + 1;`

`count = count + 1`을 가장 선호한다. 

##### 4. `if (isLogin) {}` vs `if (isLogin === true) {}`

`if (isLogin === true) {}`를 선호한다. 
isLogin이 `boolean` 값으로만 할당이 허용되는 TS 환경이면 전자도 상관없다.   
하지만 JS 환경이라면 isLogin에 `boolean` 외에도 `number` 값으로 0, 1 혹은 'test'가 들어온다면 0은 false, 1과 'test'는 true로 느슨하게 통과하게 된다.   
isLogin이 로그인 API 호출 직후에 redirect를 결정하는 분기점이라면 더더욱 후자를 사용할 것.

##### 5. `isLogin && <HelloWanted />` vs `isLogin ? <HelloWanted /> : <></>` vs `isLogin ? <HelloWanted /> : null` vs `isLogin ? <HelloWanted /> : undfined`

`isLogin && <HelloWanted />` 를 선호한다. `falsy`일 경우 따라 노출되는 게 없다면 삼항 연산자를 쓸 이유가 없다고 생각한다.
