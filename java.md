[TOC]



------



# Leran Java



------



## 변수 Variable

### 1. 변수 variable

#### 1.1. 변수란?

* 값을 저장할 수 있는 메모리상의 공간

* 이 공간에 저장된 값은 변경될 수 있기 때문에 '변수'라는 수학용어의 정의와 상통하는 면이 있음

  > "변수란, 단 하나의 값을 저장할 수 있는 메모리 공간"

* 하나의 변수에 단 하나의 값만 저장 가능!

  * 따라서 새로운 값 저장하면 기존의 값은 사라짐

#### 1.2. 변수의 선언과 초기화 

* 변수를 사용하기 위해 먼저 변수를 선언해야 함

* 선언 방법은 아래와 같다

  ```java
  int age; // age 라는 이름의 int type 변수 선언
  ```

* 변수타입

  * 변수에 저장될 값이 어떤 `type` 인지를 지정하는 것
  * 저장하고자 하는 값의 종류에 맞게 변수의 타입을 선택해서 적으면 됨
  * 자바는 정수형, 실수형, 문자형 등 다양한 타입을 제공

* 변수이름

  * 말 그대로 변수에 붙인 이름
  * 변수는 `값을 저장할 수 있는 메모리 공간`이므로 변수의 이름은 메모리 공간에 이름 붙여주는 것
  * 이름을 붙여줌으로써 그 이름을 이용해 저장공간(변수)에 값을 저장하고, 저장된 값 읽어올 수 있는 것
  * 같은 이름 여러개 X
  * 서로 구별되어야 함

* 변수를 선언하면 메모리의 빈 공간에 **변수타입**에 알맞은 크기의 저장공간 확보

* 앞으로 이 저장공간은 **변수이름**을 통해 사용할 수 있게 됨

  

* 변수의 초기화

  * 변수를 선언한 이후부터는 변수를 사용할 수 있으나

  * 그 전에 반드시 변수를 `initialization`(초기화) 해야 함

  * 메모리는 여러 프로그램이 공유하는 자원이므로 전에 다른 프로그램에 의해 저장된 '알수 없는 값'(쓰레기값, garage value)이 남아있을 수 있기 때문

  * 변수에 값을 넣을 때는 대입 연산자 `=` 를 사용

  * 수학에서는 양변 값 같다는 의미

  * 자바에서는 오른쪽 값을 왼쪽(변수)에 저장하라는 뜻

  * 따라서 대입연산자의 왼쪽에는 반드시 변수가 와야 함

    ```java
    int age = 25; // 변수 age를 선언하고 25로 초기화 한다.
    ```

  * `코드 1`

    ```java
    int a;
    int b;
    int x = 0;
    int y = 0;
    ```

  * `코드 2`

    ```java
    int a, b;
    int x = 0, y = 0;
    ```

  * 위의 `코드 1`과 `코드 2` 는 서로 같은 의미의 다른 코드

  * 변수는 한 줄에 하나씩 선언하는 것이 보통이지만

  * `타입이 같은 경우` 콤마 `,` 를 구분자로 여러 변수를 한 줄에 선언하기도 함

  * 변수의 종류에 따라 변수의 초기화를 생략할 수 있는 경우도 있지만

  * 변수는 사용되기 전에 적절한 값으로 초기화 하는 것이 좋다.

    > 변수의 초기화란, 변수를 사용하기 전에 처음으로 값을 저장하는 것

  * 예제 2-1
  
    ```java
    public class VarEx1 {
    	public static void main(String arg[]) {
    		int year = 0;
    		int age = 14;
    		
    		System.out.println(year);
    		System.out.println(age);
    		
    		year = age + 2000;
    		age = age + 1;
    		
    		System.out.println(year);
    		System.out.println(age);
    	}
    }
    ```
  
    * 두 개의 변수 age와 year를 선언한 다음
    * 값을 저장하고 출력하는 간단한 예제
    * 먼저 변수 선언부분을 보면, 변수 year와 age를 각각 0과 14로 초기화 하였음
    * 그 다음 문장은 변수 age에 저장된 값에 2000을 더한 다음
    * 그 결과를 변수 year 에 저장하라는 뜻
    * 이 문장이 처리되는 과정을 단계별로 보면
    * year = age + 2000;
    * year = 14 + 2000; → 변수 age에 저장된 값(14)를 읽어와서 식에 사용
    * year = 2014;
  
* 두 변수의 값 교환하기

  * ```java
    int x = 10;
    int y = 20;
    ```

  * 위와 같이 변수가 선언되어 있을 때, x y 를 교환하는 방법은??

  * 임시 저장소 사용!

  * ```java
    int x = 10;
    int y = 20;
    int temp;
    ```

  * ```java
    tmp = x;
    x = y;
    y = tmp;
    ```

  * 두 변수의 값을 교환하는 것은

  * like 두 컵에 담긴 내용물 바꾸려면 빈 컵 하나가 더 필요한 것

  * ```java
    public class VarEx2 {
    	public static void main(String arg[]) {
    		// x 와 y 의 값 변경하기
    		int x = 10, y = 20;
    		int tmp;
    		
    		System.out.println("x:"+ x + " y:" + y);
    		
    		tmp = x;
    		x = y;
    		y = tmp;
    		
    		System.out.println("x:"+ x + " y:" + y);
    	}
    }
    ```

  * 덧셈연산자 `+` 는 두 값을 더하기도 하지만

  * 위와 같이 문자열과 숫자를 하나로 결합하기도 함

  * 문자열은 큰따옴표`""` 로 묶은 연속된 문자를 말함

#### 1.3. 변수의 명명규칙

* `변수의 이름`처럼 프로그래밍에서 사용하는 모든 이름은 `식별자(identifier)`라고 함
* 식별자는 같은 영역 내에서 서로 구분(식별)될 수 있어야 함
* 따라서 식별자를 만들 때는 다음과 같은 규칙을 지켜야 함
  1. 대소문자가 구분되며 길이에 제한 없음
     - True 와 true 는 서로 다른 것으로 간주
  2. 예약어를 사용해서는 암됨
     - true는 예약어라서 사용할 수 없지만, True는 가능
  3. 숫자로 시작해선 안됨
     - top10은 허용하지만, 7up은 허용 X
  4. 특수문자는 `_`와 `$`만 허용
     - $harp은 허용되지만, S#arp은 허용 X
* 필수적이지는 않지만 자바 프로그래머 convention 은 다음과 같은 규칙들이 있음
  1. 클래스 이름의 첫글자는 항상 대문자로 함
     - 변수와 메서드의 이름의 첫 글자는 항상 소문자
  2. 여러 단어로 이루어진 이름은 단어의 첫 글자를 대문자로 함
     - ex) lastIndexOf, StringBuffer
  3. 상수의 이름은 모두 대문자로 함, 여러 단어로 이루어진 경우 `_`로 구분
     - PI, MAX_NUMBER

* 변수의 이름은 짧을수록 좋음

* 하지만 약간 길더라도 용도를 알기 쉽게 `의미있는 이름`으로 하는 것이 바람직함

* 변수의 선언문에 주석으로 변수에 대한 정보를 주는 것도 좋은 생각

* ```java
  int curPos = 0;  // current position
  int lstPos = -1;  // last position
  ```



### 2. 변수의 타입

* 우리가 주로 사용하는 변수 값(data)의 종류(type)는 크게 `문자`와 `숫자`로 나눌 수 있음
* 숫자는 다시 `정수`와 `실수`로 나눌 수 있음
* 이러한 값의 종류에 따라 값이 저장될 공간의 크기와 저장형식을 정의한 것이 data type 임
* 자료형에는
  * 문자형 - char
  * 정수형 - byte, short, int, long
  * 실수형 - float, double
  * 등이 있음
* 변수를 선언할 때는 저장하려는 값의 특성을 고려하여 가장 알맞은 자료형을 변수의 타입으로 선택

#### 기본형과 참조형

* 자료형은 크게 `기본형`과 `참조형` 두 가지로 나눌 수 있음
* 기본형 변수 : 실제 값(data)를 저장
* 참조형 변수 : 어떤 값이 저장되어 있는 `주소(memory address)`를 값으로 가짐
* 자바는 C언어와 달리 참조형 변수 간의 연산을 할 수 없으므로 실제 연산에 사용되는 것은 모두 기본형 변수

