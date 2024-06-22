# 챕터 33 : 결론

## 코드 정리가 먼저인지 판단하는법

* 비용 : 코드를 정리하면 비용이 줄까?
* 수익 : 코드를 정리하면 수익이 더 커질까?
* 결합도 : 코드를 정리하면 변경에 필요한 요소의 수가 줄어드나?
* 응집도 : 코드를 정리하면 변경을 더 작고 좁은 범위로 집중시켜 더 적은 수의 요소만 다룰 수 있나?

하지만 가장 중요한것은 본인, 코드를 정리하면 더 행복해지는가? 그럴 수 있다.

## 코드 정리에 집착하지 않기

* 때때로 들뜬 기분에 휩싸여 코드 정리가 최우선으로 생각할 수 있음.
* 결합도는 코드 정리 작업이 다음 코드 정리 작업으로 이어지게 함
    * 소프트웨어 설계의 프링글스, 한번 시작하면 멈출 수 없음
* 코드 정리는 다음 동작 변경을 가능하게 함
    * 그러나 변경을 기다리는 누군가가 폭발하지 않도록 나중에 해야할 때가 있음
* 혼자서 프로그래밍 하는 경우는 거의 없다
    * 여러분과 같은 사람을 대신하여 설계할 준비를 하고 있다는 사실을 명심

| 누구?          | 언제?                  | 무엇을?      | 어떻게?           | 왜?       |
|--------------|------------------------|--------------|------------------|----------|
| 여러분          | 몇 분에서 몇 시간      | 코드 정리    | 구조나 동작 변경 | 결합도와 응집도 |
| 여러분과 동료 프로그래머 | 몇 일에서 몇 주      | 리팩터링      | 주간 단위 계획   | 멱법칙      |
| 모든 이해관계자     | 몇 달에서 몇 년       | 아키텍처 진화| 동적 균형        | ?        |

**코드 정리를 먼저 하실 건가요?** 아마도요. 여러분을 위해서 충분히 그럴만한 가치가 있다.