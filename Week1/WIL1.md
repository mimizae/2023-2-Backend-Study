# GDSC 과제 (Week1)

(1) 자바와 객체 지향 프로그래밍에 대해 정리하기

# Java와 객체 지향 프로그래밍

## 자바?

“썬 마이크로시스템즈에서 개발하여 1996년 1월에 공식적으로 발표한 객체지향 프로그래밍 언어”

**자바의 특징**

1. 운영체제에 독립적이다.
•WORA (Write Once, Run Anywhere) : 자바로 작성된 프로그램은 운영체제와 하드웨어에 관계없이 실행 가능하다.
•JVM을 이용한다.
_JVM이란? JVM(Java Virtual Machine)은 자바 애플리케이션을 실행하는 데 사용되는 가상 머신
2. 객체지향언어이다.
•상속, 캡슐화, 다형성이 잘 적용된 순수한 객체지향언어
•재사용성과 유지보수의 용이성
3. 자동 메모리 관리(Garbage Collection)
4. 네트워크와 분산처리를 지원한다.
5. 멀티쓰레드를 지원한다.
6. 동적 로딩을 지원한다.

## **객체지향 프로그래밍?**

“객체지향은 실세계를 직접적이고 직관적으로 모델링 할 수 있는 패러다임”

객체지향 프로그래밍이란, 현실 속에 존재하는 사물을 최대한 유사하게 모방해 소프트웨어 내부로 옮겨오는 작업이기 때문에, 그 결과물인 객체지향 소프트웨어는 실세계의 투영이며, 객체란 현실 세계에 존재하는 사물에 대한 추상화이다.

즉, 프로그래밍에서 필요한 데이터를 추상화 시켜 상태와 행위를 가진 객체로 만들고, 객체들간의 상호작용을 통해 로직을 구성하는 프로그래밍 방법이다.

**객체지향 프로그래밍 장점과 단점**

장점
•코드의 재사용성이 높다.
•유지보수가 쉽다.
•대형 프로젝트에 적합하다.

단점
•처리 속도가 상대적으로 느리다.
•객체가 많으면 용량이 커질 수 있다.
•설계 시 많은 노력과 시간이 필요하다.

**객체지향 프로그래밍 특징**

1. 추상화
•객체에서 공통된 속성과 행위를 추출 하는 것
•공통의 속성과 행위를 찾아서 타입을 정의하는 과정
•추상화는 불필요한 정보는 숨기고 중요한 정보만을 표현함으로써 프로그램을 간단하게 만드는 것
2. 캡슐화
•데이터 구조와 데이터를 다루는 방법들을 결합 시켜 묶는 것 (변수와 함수를 하나로 묶는 것을 뜻함)
•낮은 결합도를 유지할 수 있도록 설계하는 것
•속성과 기능을 정의하는 변수와 메소드를 클래스라는 캡슐에 넣어서 분류하는 것으로 재사용이 원활하다는 장점이 있고 캡슐화를 통해서 정보은닉을 활용 할 수도 있다. (접근제어자의 활용)
3. 상속
•클래스의 속성과 행위를 하위 클래스에 물려주거나 하위 클래스가 상위 클래스의 속성과 행위를 물려받는 것을 말한다
•새로운 클래스가 기존의 클래스의 데이터와 연산을 이용할 수 있게 하는 기능

`상속의 장점`

- 범용적인 사용이 가능하다
- 재사용으로 인한 코드가 줄어든다
- 자료와 메서드의 자유로운 사용 및 추가가 가능하다
단점
- 상위 클래스의 변경이 어려워진다
- 불필요한 클래스가 증가할 수 있다
- 상속이 잘못 사용될 수 있다

1. 다형성
•하나의 변수명, 함수명이 상황에 따라 다른 의미로 해석 될 수 있는 것
•어떠한 요소에 여러 개념을 넣어 놓는 것
객체 지향 프로그래밍은 하나의 클래스 내부에 같은 이름의 행위를 여러개 정의하거나 상위 클래스의 행위를 하위 클래스에서 재정의하여 사용할 수 있기 때문에 다형성이라는 특징을 갖게 된다.

1. 오버라이딩
•상위 클래스가 가지고 있는 메소드를 하위 클래스가 재정의해서 사용하는 것
2. 오버로딩
•같은 이름의 메서드가 인자의 개수나 자료형에 따라 다른 기능을 하는 것

```java
(2) 조건에 맞춰 프로그램을 구현하기

<사칙연산에 대한 코드> 

public interface Calculator {
    int add(int num1, int num2);
    int subtract(int num1, int num2);
    int multiply(int num1, int num2);
    int divide(int num1, int num2);
}

public class CalculatorImpl implements Calculator {
    public int add(int num1, int num2) {
        return num1 + num2;
    }
    public int subtract(int num1, int num2) {
        return num1 - num2;
    }

    public int multiply(int num1, int num2) {
        return num1 * num2;
    }
    public int divide(int num1, int num2) {
        if (num2 == 0) {
            throw new ArithmeticException("나누는 수는 0이 될 수 없습니다.");
        }
        return num1 / num2;
    }

    public static void main(String[] args) {
        Calculator calculator = new CalculatorImpl();
        
        int num1 = 1234;
        int num2 = 4321;
        int num3 = 911;
        int num4 = 170;
        int num5 = 2;
        int num6 = 3;
        int num7 = 33;
        int num8 = 11;
        
        int additionResult = calculator.add(num1, num2);
        int subtractionResult = calculator.subtract(num3, num4);
        int multiplicationResult = calculator.multiply(num5, num6);
        int divisionResult = calculator.divide(num7, num8);
        
        System.out.println(num1 + " + " + num2 + " = " + additionResult);
        System.out.println(num3 + " - " + num4 + " = " + subtractionResult);
        System.out.println(num5 + " * " + num6 + " = " + multiplicationResult);
        System.out.println(num7 + " / " + num8 + " = " + divisionResult);
    }
}

<동물 출력에 관한 코드>

public class Animal {
    public static void main(String[] args) {
        System.out.println("cat says Meow!");
        System.out.println("dog says Woof!");
    }
}
```
