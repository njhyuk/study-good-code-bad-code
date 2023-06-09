# 4. 오류

* 시스템이 복구할 수 있는 오류 vs 복구 할 수 없는 오류
* 신속하게 실패하고 분명하게 실패함
* 오류를 전달하기 위한 다양한 기법, 선택을 위한 고려 사항

## 4.1 복구 가능성

`복구할 수 있는 오류 vs 복구할 수 없는 오류` 구분 방법 및 설명

## 4.1.1 복구 가능한 오류

* 사용자 입력 오류 : 오류메세지 제공 및 재요청
* 네트워크 오류 : 대기 및 재시도
* 중요하지 않은 작업 오류 : 통계 기록

> 🤔 사용자 입력 오류는 오류를 클라이언트에게 리턴하고 프로그램을 종료하는데, 복구 가능한 오류인가?

## 4.1.2 복구할 수 없는 오류

* 코드와 함께 추가되어야 하는 리소스가 없다.
* 어떤 코드가 다른 코드를 잘못 사용한다.
  * 잘못된 입력 인수로 호출
  * 일부 필요한 상태가 사전에 초기화 되지 않음
* 복구할 수 없는오류 의 가장 합리적인 방법
  * 개발자가 빠르게 확인하여 조치할 수 있게 하는 것
    * 신속한 실패(failing fast), 요란한 실패(failing loudly)

## 4.1.3 호출하는 쪽에서만 오류 복구 가능여부를 알 때가 많다

대부분의 오류는 한 코드가 다른 코드를 호출 할 때 발생하여 다음을 고려해야 함.

* 오류로부터 복구하기를 호출하는 쪽에서 원하는가?
* 만약 그렇다면 오류를 처리할 필요가 있다는 것을 호출하는 쪽에서 어떻게 알 수 있는가?


### 예제 4.1

프로그램이 복구 할 수 있는지 여부는 함수를 호출하는 쪽 에서만 알 수 있다.

```java
class PhoneNumber {
    static PhoneNumber parse (String number) {
        if (!isValidPhoneNumber (number)) {
            /* 에러를 처리하기 위한 코드 */
        }
    }
}
```

호출부 예시 1 - 회사 전화번호 하드코딩 파싱 - 복구할 수 없음

```java
PhoneNumber getHeadOfficeNumber() {
    // 
    return PhoneNumber.parse("01234typo56789")
}
```

호출부 예시 2 - 사용자 인풋 클라이언트 - 유저에게 오류를 리턴하여 복구

```java
PhoneNumber getUserPhoneNumber(UserInput input) {
    return PhoneNumber.parse(input.getPhoneNumber())
}
```

## 4.1.4 호출하는 쪽에서 복구하고자 하는 오류에 대해 인지하도록 하라

* 이 클래스를 사용하는 코드는 구현 세부사항을 알 필요가 없음.
  * `PhoneNumber` 클래스는 전화번호 규칙을 클라이언트가 모르게 하기 위해 만들어짐.
* 호출하는 사람은 전화번호 형식에 전문적 지식이 없다.
  * 잘못된 형식의 전화번호가 있는지 모를 수 있음.
  * 또는 호출할때 유효성 검사가 이루어 질 것으로 예상함.
* 그래서 어떻게?
  * 전화번호 클래스 작성자는 오류가 발생할 가능성을 인지시켜야함
  * 자세한 방법은 이어서 설명...



