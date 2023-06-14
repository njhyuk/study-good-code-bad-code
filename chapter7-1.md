# 7 코드를 오용하기 어렵게 만들라
코드를 쉽게 오용할 수 있는 경우와 오용하기 어렵게 만드는 기법 설명

# 7.1 불변 객체로 만드는 것을 고려하라
* 가변 객체는 추론하기 어렵다.
	* 상자에 있는 봉인씰을 예시로
	* 상자 안에 들어 있는 것과 출처를 신뢰 할 수 있음
	* 씰이 없다면 오물이 있을 수 있음
	* 불변은 봉인씰과 비슷하다.
* 가변 객체는 다중 스레드에서 문제가 발생할 수 있다.
	* 한 스레드가 객체를 읽는 동안 다른 스레드가 객체를 수정

## 7.1.1 가변 클래스는 오용하기 쉽다
* 가변적으로 만드는 일반적인 방법 : Setter 함수 제공
* 예제 7.1 에서 setFont 를 열어둔 예시
* 예제 7.2 에서 생성자로 폰트를 선언했지만, render 함수에서 오용한 예시

## 7.1.2 해결책: 객체를 생성할 때만 값을 할당하라
* 모든 값이 객체의 생성시에만 제공되고 변경할 수 없게 하라
* 예제 7.3 에서 set을 지우고 생성자로 에서만 폰트 선언
* 예제 7.4 에서 렌더에 재정의 하고 싶은경우, 객체를 복사하는 메소드 사용

## 7.1.3 해결책: 불변성에 대한 디자인 패턴을 사용하라
* 일부 값이 필요하지 않거나, 불변적인 클래스를 가변 시키고 싶을때는?
	* 빌더 패턴
	* 쓰기시 복사 패턴

### 빌더 패턴
* 한클래스를 두개로 나누는 효과
	* 값을 하나씩 설정할 수 있는 빌더 클래스
		* 필수값 : 생성자 - 예제 7.5 TextOptionsBuilder(Font font)
		* 선택값 : 세터 함수
	* 빌더에 의해 작성된 불변적 읽기 전용 클래스
		* 예제 7.5 - 읽을수 만 있는 TextOption 클래스

### 쓰기 시 복사 패턴
* 예제 7.6 : withFont 함수
	* 객체의 기존 fountSize 값과 파라미터로 받은 newFont 로 객체 new