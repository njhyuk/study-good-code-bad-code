# 5-2 주석문의 적절한 사용

* 코드가 무엇을 하는지 설명
* 코드가 왜 그 일을 하는지 설명
* 사용지침 등 기타 정보 제공

코드의 기능을 설명하기 위해 낮은 층위르 주석문을 많이 추가해야 한다면? 가독성이 떨어진다는 신호.

코드가 왜 그 일을 하는지 이유나 배경을 설명하는 주석문은 유용할때가 많다. (코드로 알 수 없음)

## 5.2.1 중복된 주석문은 유해할 수 있다

* (예제 5.4) 코드 자체로 설명 되서 쓸모 없는 주석, 더 나쁠 수 있음.
* 주석문을 유지보수 해야함, 코드를 지저분하게 만듦
* 주석을 지우는게 좋은 예시

## 5.2.2 주석문

* 주석문으로 가독성 높은 코드를 대체할 수 없다

* (예제 5.5) 배열의 특정 인덱스가 이름 또는 성, 코드로 알기 어려움, 주석이 유용해 보이지만 진짜 문제는 코드 가독성 문제.
* (예제 5.6) 에서 private 함수 호출로 개선함.

## 5.2.3 주석문은 코드의 이유를 설명하는데 유용하다

코드로 알수 없는 것들 (코드가 왜 그 일을 하는지 설명)

* 제품 또는 비즈니스 의사 결정
* 이상하고 명확하지 않은 버그에 대한 해결책
* 의존하는 코드의 예상을 벗어나는 동작에 대처

(예제 5.7) 레거시와 이슈티켓을 기재하여 배경을 설명함

## 5.2.4 주석문은 유용한 상위 수준의 요약 정보를 제공할 수 있다

* 책을 읽으려고 하는데 모든 단락 앞에 한문장 짜리 줄거리? 성가시고 읽기 어려운 책
  * 코드가 무엇을 하는지 설명하는 주석문
* 각 장의 시작 부분에 간략하게 요약해서 보여주면? 독자는 빠르게 확인 가능, 흥미 유발
  * 클래스가 하는 일을 요약한 상위수준 주석문

유용한 상위 수준에서의 개략적인 문서

* 클래스가 수행하는 작업 및 다른 개발자가 알고 있어야 할 중요 세부사항을 개괄적 설명
* 함수에 대한 입력 매개변수 도는 기능 설명
* 함수의 반환값이 무엇을 나타내는지 설명











