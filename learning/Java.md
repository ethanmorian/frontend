# Java

## 클래스와 객체

클래스로 객체 정의 및 생성

객체 = 속성(변수) + 기능(메서드)

객체 = 모든 인스턴스

인스턴스 = 특정 클래스로 생성된 객체

인스턴스화 = 클래스 > 인스턴스(객체)

소스파일명은 public class 명과 일치해야 함

하나의 소스파일엔 하나의 public class 만 존재

## 객체 생성

인스턴스 = `클래스 참조 변수 = new 생성자();`

`변수.변수 = ;`

`참조 변수.메서드();`

다수의 참조 변수로 하나의 인스턴스 참조 가능

`참조 변수 = 참조 변수;`

## 객체 배열

### 객체 배열 생성 방법1

```java 
클래스 참조 배열[] = new 생성자[];

참조 배열[0] = new 생성자();

참조 배열[1] = new 생성자();

참조 배열[2] = new 생성자();
```

### 객체 배열 생성 방법2

- `클래스 참조 배열[] = {new 생성자(), new 생성자(), new 생성자()};`

## 클래스란

클래스 = 데이터 + 함수

## 선언 위치에 따른 변수 종류

### 클래스 영역 = 선언문만 가능

- iv(instance variable) = 인스턴스가 생성되었을 때 생성
- cv(class variable) = static + iv 형태, 클래스가 메모리에 올라갈 때 생성

### 메서드 영역

- lv(local variable) = 변수 선언문이 수행되었을 때 생성, 메서드 종료시 사용 불가

## 클래스 변수와 인스턴스 변수

### 인스턴스 변수

- 개별 속성
- `클래스 참조변수 = new 생성자();`
- 객체 생성과 비례해 생성

### 클래스 변수

- 공통 속성

```java 
// 참조 변수도 사용 가능하나 권장하지 않음
클래스 참조 변수 = new 생성자();

//권장하는 방법
클래스.속성 이름 = 값;
```

- 1개만 존재
- 객체 생성없이 사용 가능, 자동으로 생성

## 메서드란?

문장들을 묶어 놓은 것

중복된 코드를 메서드로 변환해 메서드 호출을 통해 코드 간결화

작업단위로 문장들을 묶어서 이름 붙인 것

```java 
반환 타입 메서드 이름 (반환 타입 매개변수1, 반환 타입 매개변수2) {
    반환 타입 반환값 = 매개변수1 + 매개변수2;
    return 반환값;
}
```

## 메서드 호출

메서드 호출 방법 = `메서드 이름(값1, 값2)`

메서드는 클래스 영역에만 정의 가능

## return 문

실행 중인 메서드를 중지하고 호출한 곳으로 복귀

반환 타입이 void 인 경우 생략 가능

if 문의 경우 참과 거짓의 두 가지 경우의 return 문이 필요

메서드의 반환 타입과 반환값의 반환 타입 일치

## 호출 스택(call stack)

FILO = First In Last Out, 선입 후출

## 기본형 매개변수

변수 값 읽기만 가능(Read only)


## 참조형 매개변수

변수 값 읽고 변경 가능(Read and write)

반환 타입이 참조형인 경우 객체의 주소 반환

같은 클래스 안 or static 메서드 = 참조 변수 없이 호출 가능

## static 메서드와 인스턴스 메서드

### static 메서드(클래스 메서드)

- 객체 생성 없이 `클래스 이름.메서드 이름();`으로 호출
- 메서드 안에서 인스턴스 변수 사용 불가
- 클래스 변수는 사용 가능
- 인스턴스 메서드 호출 불가

### 인스턴스 메서드

- 인스턴스 생성 후 `참조 변수. 메서드 이름();`으로 호출
- 메서드 안에서 인스턴스 변수 사용 가능

### static 을 붙이는 기준

- 인스턴스 변수를 사용하지 않는 메서드
- 속성 중 공통 속성

## 오버로딩(Overloading)

한 클래스 안에 같은 이름의 메서드 여러 개를 정의한 것

### 오버로딩 성립 조건

- 메서드 이름이 같아야 한다
- 매개변수의 개수 또는 타입이 달라야 한다
- 반환 타입은 영향이 없다

메서드 이름 = 대부분 동사

## 생성자(constructor)

인스턴스가  생성될 때마다 호출되는 '인스턴스 초기화 메서드'

`클래스 이름 참조 변수 = new 생성자();`

생성자의 이름은 클래스와 같아야 함

리턴값이 없다(void 안 붙임)

모든 클래스는 1개 이상의 생성자가 있어야 함

### 기본 생성자(default constructor)

- 매개변수가 없는 생성자
- 생성자가 하나도 없을 때만 컴파일러가 자동 추가
- 기본 생성자는 만드는 게 원칙
- `클래스 이름() {}`
- 기본 생성자 없이 매개변수가 있는 생성자가 있을 경우 에러 발생

### 매개변수가 있는 생성자

```java 
클래스 이름 {
    반환 타입 변수1
    반환 타입 변수2
    
    생성자() {} // 기본 생성자
    생성자(반환 타입 변수3, 반환 타입 변수4) { // 매개변수가 있는 생성자
        변수1 = 변수3;
        변수2 = 변수4;
    }
}    
```

- 매개변수가 있을 경우 코드가 더 간결해짐

```java 
// 매개변수가 있는 생성자가 없을 경우
클래스 이름 참조 변수 = new 생성자();
참조 변수.변수1 = 값1;
참조 변수.변수2 = 값2;

// 매개변수가 있는 생성자가 있을 경우
클래스 이름 참조 변수 = new 생성자(값1, 값2);
```

- `클래스 이름 참조 변수 = new 생성자();`
- 클래스 이름 참조 변수 = 참조 변수 생성
- new = 객체 생성
- 생성자() = 생성자 호출 후 객체 초기화

## 생성자 this()

같은 클래스에 생성자 안에서 다른 생성자를 호출할 때 사용

첫 줄에서만 사용 가능

## 참조 변수 this

인스턴스 자신을 가리키는 참조 변수

인스턴스 메서드에서만 사용 가능

지역 변수와 인스턴스 변수를 구별할 때 사용

this. 이 붙으면 인스턴스 변수

같은 클래스 안에선 생략 가능

이름이 같을 경우 생략 불가

인스턴스 주소 저장되어 있음

선언 안 해도 사용 가능

## 변수의 초기화

지역 변수는 수동 초기화 해야 함

멤버 변수(인스턴스 변수, 클래스 변수)는 자동 초기화 됨

## 멤버 변수의 초기화

명시적 초기화(=) = 선언 시 대입 연산자를 통해 초기화

### 초기화 블럭 = 복잡한 초기화 시 사용

- 인스턴스 초기화 블럭 = {}

- 클래스 초기화 블럭 = static {}

생성자 = 복잡한 초기화 시 사용

인스턴스 변수 초기화 = 생서앚

클래스 변수 초기화 = static {}

클래스 변수 초기화 시점 = 클래스가 처음 로딩될 때 한 번

인스턴스 변수 초기화 시점 = 인스턴스가 생성될 때 마다

클래스 변수 초기화 > 인스턴스 변수 초기화

자동 초기화(0) > 간단 초기화(=) > 복잡 초기화({}, static {})

## 상속

기존의 클래스로 새로운 클래스를 작성하는 것(코드의 재사용)

두 클래스를 부모와 자식으로 관계를 맺어주는 것

```java 
class 부모 클래스 {
    반환 타입 값1;
}
class 자식 클래스 extends 부모 클래스 {
    // 자식 클래스는 부모 클래스로부터 상속
    // 반환 타입 값1;
    반환 타입 값2;
}
```

자손은 조상의 모든 멤버를 상속받는다(생성자, 초기화 블럭 제외)

자손의 멤버 개수는 조상보다 적을 수 없다(같거나 많다)

자손의 변경은 조상에 영향을 미치지 않는다

## 포함 관계

포함 = 클래스의 멤버로 참조 변수를 선언하는 것

```java 
class 클래스1 {
    반환 타입 값1;
}
class 클래스2 { // 클래스2는 클래스1을 포함
    클래스1 참조 변수 = new 클래스1();
    반환 타입 값2;
}
```

## 클래스 간의 관계 설정하기

대부분 포함 관계, 상속은 제약이 있어서 꼭 필요한 경우만 사용

## 단일 상속

하나의 부모로부터 상속 가능

다중 상속 = 비중이 높은 클래스 하나를 상속으로 나머지는 포함

## Object 클래스 - 모든 클래스의 조상

부모가 없는 클래스는 자동으로 Object 클래스를 상속 받음

모든 클래스는 Object 클래스에 정의된 11개의 메서드를 상속 받음

## 오버라이딩(overriding)

상속받은 조상의 메서드를 자신에 맞게 변경

```java 
class 클래스1 {
    반환 타입 값1;
    반환 타입 값2;
    
    반환 타입 메서드1() {
        return '값1'+값1+'값2'+값2;
    }
}
class 클래스2 {
    반환 타입 값3;
    
    반환 타입 메서드1() {
    return '값1'+값1+'값2'+값2+'값3'+값3;
    }
}
```

구현부만 변경 가능, 선언부는 변경 불가

의미상 같은 작업을 수행할 때 적절

## 오버라이딩 조건

선언부가 조상 클래스의 메서드와 일치

접근 제어자를 조상 클래스의 메서드보다 좁은 범위로 변경 불가

예외는 조상 클래스의 메서드보다 많이 선언 불가

## 참조 변수 super

객체 자신을 가리키는 참조 변수, 인스턴스 메서드(생성자) 내에서만 존재

조상의 멤버를 자신의 멤버와 구별할 때 사용

## super() 조상의 생성자

조상의 생성자를 호출할 때 사용

조상의 멤버는 조상의 생성자를 호출해서 초기화

```java 
class 부모 클래스 {
    반환 타입 값1, 값2;
    
    생성자1 (반환 타입 값1, 반환 타입 값2) {
        this.값1 = 값1;
        this.값2 = 값2;
    }
}

class 자식 클래스 extends 부모 클래스 {
    반환 타입 값3;
    
    생성자2 (반환 타입 값1, 반환 타입 값2, 반환 타입 값3) {
        super(값1, 값2); // 조상 클래스 생성자 생성자1 호출 
        this.값3 = 값3;
    }
}
```

모든 생성자는 첫 줄에 다른 생성자를 호출

그렇지 않으면 컴파일러가 생성자 첫 줄에 super(); 를 삽입

## 패키지(package)

서로 관련된 클래스 묶음

클래스 = 클래스 파일, *.class

패키지 = 폴더, 클래스의 실제 이름은 패키지를 포함

패키는 소스파일의 첫 번째 문장으로 단 한 번 선언

패키지 선언 = `package 패키지 이름;`

같은 소스 파일의 클래스들은 모두 같은 패키지에 속하게 된다

패키지 선언이 없으면 이름없는(unnamed) 패키지에 속하게 된다 

## 클래스 패스(classpath)

클래스 파일의 위치를 알려주는 경로

환경변수로 classpath 로 관리하며 경로간의 구분자는 ';'를 사용

classpath(환경변수)에 패키지의 루트를 등록해줘야 함

## import 문

클래스를 사용할 때 패키지 이름을 생략할 수 있다

컴파일러에게 클래스가 속한 패키지를 알려준다

java.lang 패키지는 import 하지 않아도 사용 가능

import 문 = `import 패키지명.클래스명;`

import 문은 패키지문과 클래스 선언 사이에 선언

import 문은 컴파일 시에 처리되므로 프로그램의 성능에 영향 없음

## static import 문

static 멤버를 사용할 때 클래스 이름을 생략 가능

`import static 패키지명.클래스명;`

## 제어자(modifier)

클래스와 클래스의 멤버(멤버 변수, 메서드)에 부가적인 의미 부여

하나의 대상에 여러 제어자 사용 가능(접근 제어자는 하나만)

## static -클래스의 , 공통적인

### static 멤버 변수

- 모든 인스턴스에 공통적으로 사용되는 클래스 변수로 변환
- 클래스 변수는 인스턴스를 생성하지 않고 사용 가능
- 클래스가 메모리에 로드될 때 생성

### static 메서드

- 인스턴스 생성하지 않고 호출 가능

- static 메서드 안에서 인스턴스 멤버 직접 사용 불가

## final - 마지막의, 변경 불가

### final 클래스

- 변경 불가, 확장 불가, 다른 클래스에 상속 불가

### final 메서드

- 변경 불가, 오버라이딩 통해 재정의 불가

### final 멤버 변수, final 지역 변수

- 값을 변경할 수 없는 상수로 변환

## abstract - 추상의, 미완성의

abstract 클래스 = 클래스 내에 추상 메서드가 선언 되있음을 알림

abstract 메서드 = 선언부만 작성한 추상 메서드임을 알림

```java 
abstract class 클래스1 {
    abstract 반환 타입 메서드1();
} 
```

추상 클래스는 인스턴스 생성 불가

추상 클래스를 상속 받아 완전한 클래스를 만든 후 인스턴스 생성 가능

## 접근 제어자

private = 같은 클래스 내에서만 접근 가능

(default) = 같은 패키지 내에서만 접근 가능

protected = 같은 패키지 내에서, 다른 패키지의 자손 클래스에서 접근 가능

public = 접근 제한 없음

public > protected > (default) > private

class = public or (default)

## 캡슐화와 접근 제어자

## 접근 제어자 사용 이유

- 외부로부터 데이터 보호하기 위해
- 외부에는 불필요한 내부적으로만 사용되는 부분들을 감추기 위해

접근 제어자가 public 일 경우 직접 접근 가능

인스턴스 변수 보호를 위해 public 메서드를 통한 간접 접근

## 다형성(polymorphism)

조상 타입 참조 변수로 자손 타입 객체를 다루는 것

```java 
// 타입 불일치
조상 타입 참조 변수 = new 자손 생성자();
```

자손 타입의 참조 변수로 조상 타입의 객체를 가리킬 수 없다

```java 
class 클래스1 {
    메서드1 () {
        System.out.println("메서드1");
    }
}

class 클래스2 extends 클래스1 {
    메서드2 () {
        System.out.println("메서드2");
    }
}

class main {
    public static void main(String args[]) {
        클래스1 참조 변수1 = new 클래스2();
        클래스1.메서드1(); // 가능
        클래스1.메서드2(); // 불가능
    }
}
```

## 참조 변수의 형변환

사용할 수 있는 멤버의 개수를 조절하는 것

조상 자손 관계의 참조 변수는 서로 형변환 가능

```java 
class 클래스1 {멤버 4개}
class 클래스2 extends 클래스1 {멤버 5개}
class 클래스3 extends 클래스1 {}

// 사용 가능 멤버 5개
클래스2 참조 변수1 = new 클래스2();

// 조상인 클래스1 타입으로 형변환, 생략 가능, 사용 가능 멤버 4개 
// 클래스1 참조 변수2 = (클래스1)참조 변수1;
클래스1 참조 변수2 = 참조 변수1;

// 자손인 클래스2 타입으로 형변환, 생략 불가, 사용 가능 멤버 5개
클래스2 참조 변수3 = (클래스2)참조 변수2;

// 상속관계가 아닌 클래스 간의 형변화 불가
클래스3 참조 변수4 = (클래스3)참조 변수1;
```

```java 
클래스1 참조 변수1 = null;
클래스2 참조 변수2 = new 클래스2();

// 조상 > 자손 형변환
클래스2 참조 변수3 = (클래스2)참조 변수1();

// 자손 > 조상 형변환
클래스1 참조 변수4 = (클래스1)참조 변수3()
```

에러가 발생 여부는 인스턴스가 무엇인지가 결정

## instanceof 연산자

참조 변수의 형변환 가능여부 확인에 사용, 가능하면 true 반환

형변환 전에 반드시 확인

`자손 instanceof 조상`

## 매개변수의 다형성

참조형 매개변수는 메서드 호출 시 자신과 같은 타입 또는 자손 타입의 인스턴스를 넘겨줄 수도 있다

`조상 클래스 참조 변수 = new 자손 생성자();`

## 여러 종류의 객체를 배열로 다루기

조상 타입의 배열에 자손들의 객체를 담을 수 있다

```java 
조상 클래스 참조 배열[] = new 조상 생성자[3];
참조 배열[0] = new 자손 생성자1();
참조 배열[1] = new 자손 생성자2();
참조 배열[3] = new 자손 생성자3();
```

## 추상 클래스(abstract class)

미완성 메서드를 갖고 있는 클래스

다른 클래스 작성에 도움을 주기 위한 것, 인스턴스 생성 불가

상속을 통해 추상 메서드를 완성해야 인스턴스 생성 가능

꼭 필요하지만 자손마다 다르게 구현될 것으로 예상되는 경우

## 추상 메서드

미완성 메서드, 구현부가 없는 메서드

`abstract 반환 타입 메서드 이름();`

꼭 필요하지만 자손마다 다르게 구현될 것으로 예상되는 경우에 사용

```java 
abstract class 클래스1 { // 추상 클래스
    // 추상 메서드 2개
    abstract 리턴반환  메서드1();
    abstract 리턴반환  메서드2();
}

class 클래스2 extends 클래스1 { // 완전한 클래스
    // 부모 클래스의 모든 추상 메서드 구현 완료
    반환 타입 메서드1() { 구현 }
    반환 타입 메서드2() { 구현 }
}

abstract class 자식 클래스 extends 부모 클래스 { // 불완전한 클래스
    // 부모 클래스의 모든 추상 메서드를 구현하지 않음
    반환 타입 메서드1() { 구현 }
}
```

추상 메서드 호출 가능, 호출엔 선언부만 필요

## 추상 클래스의 작성

여러 클래스에 공통적으로 사용될 수 있는 추상 클래스를 바로 작성하거나 기존 클래스의 공통 부분을 뽑아서 추상 클래스를 만든다

추상화된 코드는 구체화된 코드보다 유연하다

## 인터페이스

추상 메서드의 집합

모든 상수 = public  static final, 일부 또는 전부 생략 가능

모든 메서드 = public abstract, 일부 또는 전부 생략 가능

```java 
interface 인터페이스 이름 {
    // public abstract 생략 가능
    // 메서드 이름(매개변수 목록);
    public abstract 메서드 이름(매개변수 목록);
}
```

## 인터페이스의 상속

인터페이스의 조상은 인터페이스만 가능(Object가 최고 조상 아님)

다중 상속 가능, 추상 메서드는 충돌해도 상관 없음

```java 
interface 인터페이스1 extends 인터페이스2, 인터페이스3 {}

interface 인터페이스2 {
    반환 타입 메서드1 {}
}

interface 인터페이스3 {
    반환 타입 메서드2 {}
}
```

## 인터페이스의 구현

인터페이스에 정의된 추상 메서드를 완성하는 것

```java 
class 클래스 이름 implements 인터페이스 이름{
    // 인터페이스의 정의된 메서드 모두 구현
}
```

추상 클래스를 상속받아 완성하는 것과 동일

일부만 구현하는 경우 class 앞에 abstract

인터페이스는 인스턴스 변수를 가질 수 없다

## 인터페이스를 이용한 다형성

인터페이스 타입 매개변수는 인터페이스 구현한 클래스의 인스턴스만 가능

```java 
class 클래스1 extends 클래스2 implements 인터페이스 {
    public 반환 타입 메서드1() {}
}
// 인터페이스로 클래스 인스턴스 참조 가능
// 클래스1의 멤버 중 인터페이스에 정의된 멤버만 사용 가능
인터페이스 참조 변수 = new 클래스1();
```

메서드의 반환 타입이 인터페이스일 경우 인터페이스를 구현한 인스턴스 반환

오버라이딩 규칙 = 조상보다 접근 제어자의 범위가 좁아서는 안된다

## 인터페이스의 장점

선언과 구현을 분리 가능(느슨한 결합)

개발 시간 단축(추상 메서드 호출)

표준화 가능(JDBC)

서로 관계 없는 클래스들을 관계 맺어줄 수 있다

## 디폴트 메서드와 static 메서드

```java 
interface 인터페이스 {
    // 선언부만 존재하는 추상 메서드
    반환 타입 메서드1();
    // 구현부 작성 가능한 디폴트 메서드
    default 반환 타입 메서드2() {}
}
```

### 디폴트 메서드가 기존의 메서드와 충돌할 때

- 여러 인터페이스에서 디폴트 메서드 간의 충돌 = 인터페이스를 구현한 클래스에서 디폴트 메서드를 오버라이딩
- 디폴트 메서드와 조상 클래스의 메서드 간의 충돌 = 조상 클래스가 상속되고 디폴트 메서드는 무시된다
- 잘 모르겠을 땐 오버라이딩으로 해결 가능

## 내부 클래스(inner class)

클래스 안의 클래스

```java 
class 클래스1{ // 외부 클래스
    class 클래스2{ // 내부 클래스
    }
}
```

### 내부 클래스의 장점

- 내부 클래스에서 외부 클래스의 멤버들을 쉽게 접근 가능
- 코드의 복잡성으 줄일 수 있다(캡슐화)

## 내부 클래스의 종류와 특징

내부 클래스의 종류와 유효범위(scope)는 변수와 동일

인스턴스 내부 클래스 = 인스턴스 변수

static 내부 클래스 = 클래스 변수

지역 내부 클래스 = 지역 변수

## 내부 클래스의 제어자와 접근성

내부 클래스에 제어자는 변수에 사용 가능한 제어자와 동일

```java 
class 클래스1 { // (default) or public 만 가능 
    // 내부 클래스는 private or protected 도 가능
    private class 클래스2 {}
    protected class 클래스3 {}
}
```

```java 
class 클래스1 {
    class 클래스2 { // 인스턴스 내부 클래스
        // static 변수 선언 불가
        static 반환 타입 cv = 100;
        // final static 은 상수이므로 가능
        final static 반환 타입 a = 100;
    }

    static class 클래스3 { // static 내부 클래스
        static 반환 타입 cv =200; // static 클래스만 static 멤버 정의 가능
    }
    
    반환 타입 메서드1() {
        class 클래스4 { // 지역 내부 클래스
            // static 변수 선언 불가
            static 반환 타입 cv = 300;
            // final static 은 상수이므로 가능
            final static 반환 타입 a = 300;
        }
        // 메서드 안에서 지역 내부 클래스 사용 가능
        반환 타입 i = 클래스4.a;
    }

    public static void main(String[] args) {
        System.out.println(클래스2.a);
        System.out.println(클래스3.cv);
        // 지역 내부 클래스는 메서드 내에서만 사용 가능
        //System.out.println(클래스4.a);
    }
}
```

```java 
class 클래스1 {
    class 클래스2 {} // 인스턴스 멤버
    static class 클래스3 {} // static 멤버
    
    // 인스턴스 멤버끼리 접근 가능
    클래스2 iv = new 클래스2();
    // static 멤버끼리 접근 가능
    클래스3 cv = new 클래스3();
    
    static 반환 타입 메서드1() {
        // static 멤버는 인스턴스 멤버에 접근 불가
        // 클래스2 멤버1 = new 클래스2();
        클래스3 멤버2 = new 클래스3();
        
        // 인스턴스 클래스는 외부 클래스 생성 후 생성 가능
        클래스1 외부 클래스 = 클래스1();
        클래스2 멤버1 = 외부 클래스.new 클래스2();
    }
    
    반환 타입 메서드2() { // 인스턴스 메서드
        // 인스턴스 멤버, static 멤버 모두 접근 가능
        클래스2 멤버1 = new 클래스2();
        클래스3 멤버2 = new 클래스3();
        
        // 지역 내부 클래스는 외부에서 접근 불가
        클래스4 lv = new 클래스4();
    }
    
    반환 타입 메서드3() {
        class 클래스4 {} // 지역 내부 클래스
        클래스4 lv = new 클래스4();
    }
}
```

```java 
class 클래스1 {
    private 반환 타입 iv = 0;
    static 반환 타입 cv = 0;
    
    class 클래스2 { // 인스턴스 내부 클래스
        // 외부 클래스의 private 멤버 접근 가능
        반환 타입 siv = iv;
        static 반환 타입 scv = cv;
    }
    
    static class 클래스3 { // static 내부 클래스
        // static 클래스는 외부 클래스의 인스턴스 멤버 접근 불가
        // 반환 타입 siv = iv;
        static 반환 타입 scv = cv;
    }
    
    반환 타입 메서드1() {
        // 지역변수는 메서드 종료와 동시에 삭제
        // 값이 변하지 않는 변수는 상수로 간주
        반환 타입 lv = 0;
        final 반환 타입 LV = 0;
        
        class 클래스4 { // 지역 내부 클래스
            // 지역 내부 클래스를 감싸고 있는 메서드의 상수만 사용 가능
            // 내부 클래스 객체는 메서드 종료 후에도 존재 가능
            // 반환 타입 liv1 = lv;
            반환 타입 liv2 = LV;
        }
    }
}
```

```java 
class 클래스1{
    class 클래스2 { // 인스턴스 내부 클래스
        반환 타입 iv = 100;
    }
    
    static class 클래스3 { // static 내부 클래스
        반환 타입 iv = 200;
        static 반환 타입 cv = 300;
    }
    
    반환 타입 메서드1() {
        class 클래스4 { // 지역 내부 클래스
            반환 타입 iv = 400;
        }
    }
}

class 클래스5 {
    public static void main(String[] args) {
        클래스1 oc = new 클래스1(); // 외부 클래스의 인스턴스 생성 후
        클래스1.클래스2 ii = oc.new 클래스2(); //  인스턴스 클래스의 인스턴스 생성 가능

        System.out.println(ii.iv);
        System.out.println(클래스1.클래스3.cv);
        
        // static 내부 클래스의 인스턴스는 외부 클래스를 먼저 생성하지 않아도 된다
        클래스1.클래스3 si = new 클래스1.클래스3();
    }
}
```

```java 
class 클래스1 {
    반환 타입 value = 10; // 클래스1.this.value
    
    class 클래스2 { 
        반환 타입 value = 20; // this.value
        
        반환 타입 메서드1() {
            int value = 30; // 지역변수

            System.out.println(value); // 10
            System.out.println(this.value); // 20
            System.out.println(클래스1.this.value); // 30
        }
    } // 클래스2의 끝
} // 클래스1의 끝

class 클래스3 {
    public static void main(String[] args) {
        클래스1 outer = new 클래스1();
        클래스1.클래스2 inner = 클래스1.new 클래스2();
        클래스2.메서드1();
    }
}
```

## 익명 클래스(anonymous class)

정의와 생성을 동시에 하는 이름 없는 일회용 클래스

```java 
new 조상 클래스 이름() {
    // 멤버 선언
}

new 구현 인터페이스 이름() {
    // 멤버 선언
}
```

```java 
class 클래스1 {
    // 익명 클래스
    Object iv = new Object() {반환 타입 메서드1(){}};
    // 익명 클래스
    static Object cv = new Object(){반환 타입 메서드1(){}};
    
    반환 타입 메서드1() {
        // 익명 클래스
        Object lv = new Object(){반환 타입 메서드1(){}};
    }
}
```

```java 
class 클래스1 {
    public static void main(String[] args) {
        클래스2 a = new 클래스2();
        a.메서드1(new 클래스3());
    }
}

class 클래스3 implements 인터페이스1 {
    // 클래스 내용
}

// 익명 클래스 사용 시
class 클래스1 {
    public static void main(String[] args) {
        클래스2 a = new 클래스2();
        a.메서드1(new 인터페이스1() {
           // 클래스 내용 
        });
    }
}
```

## 프로그램 오류

컴파일 에러 = 컴파일 할 때 발생하는 에러

런타임 에러 = 실행할 때 발생하는 에러

논리적 에러 = 작성 의도와 다르게 동작

## 예외 처리하기

```java 
try { // try문의 괄호 생략 불가
    // 예외가 발생할 수 있는 문장
    // 예외 발생 시 그 이후 문장은 수행되지 않음
} catch (Exception1 e1) {
    // Exception1 이 발생했을 경우 이를 처리하기 위한 문장
} catch (Exception2 e1) {
    // Exception2 이 발생했을 경우 이를 처리하기 위한 문장
} catch (ExceptionN eN) {
    // ExceptionN 이 발생했을 경우 이를 처리하기 위한 문장
}
```

## printStackTrace()와 getMessage()

Exception.printStackTrace(); = 예외 발생 당시 호출 스택에 있었던 메서드의 정보와 1예외 메시지를 화면에 출력한다.

Exception.getMessage(); = 발생한 예외 클래스의 인스턴스에 저장된 메시지를 얻을 수 있다

## 멀티 catch 블럭

```java 
try {
        ...
} catch (Exception1 e) {
    e.printStatckTrac();
} catch (Exception2 e) {
    e.printStatckTrac();
}

// 내용이 같은 catch 블럭을 하나로 합친 것
try {
        ...
} catch (Exception1 | Exception2 e) {
    e.printStatckTrac();
}
// Exception1과 Exception2가 부모 자식 관계일 경우 부모만 써도 됨
// Exception1에만 있거나 Exception2에만 있는 메서드 사용 불가
// if else 문으로 instanceof 체크 후 형변환 하면 사용 가능
```

## 예외 발생시키기

```java 
// 연산자 new 를 이용해 예외 클래스 인스턴스 생성
Exception e = new Exception("임의 발생");
// 키워드 throw 를 이용해 예외 발생
throw e;
```

## checked 예외, unchecked 예외

checked 예외 = 컴파일러가 예외 처리 여부를 체크(예외 처리 필수)

unchecked 예외 = 컴파일러가 예외 처리 여부를 체크 안함(예외 처리 선택)

## 메서드에 예외 선언하기

예외를 처리하는 방법 = try-catch 문, 예외 선언하기

메서드 호출 시 발생 가능한 예외를 호출하는 쪽에 알리는 것

```java 
// 예외를 선언하는 키워드 throws
// Exception과 그 자손 예외 발생 가능
반환 타입 메서드1 throws Exception{
        // 메서드 내용
}
```

## finally 블럭

예외 발생 여부와 관계없이 수행되어야하는 코드

```java 
try {
    // 예외가 발생할 수 있는 문장
} catch (Exception1 e1) {
    // 예외처리를 위한 문장
} finally {
    // 예외 발생 여부와 관계없이 수행되어야 하는 문장
    //  finally 블럭은 try-catch 문 맨 마지막에 위치    
}
// try 문 안에 return 문으로 try 문을 빠져나가도 finally 문은 실행됨
```

## 사용자 정의 예외 만들기

```java 
// Exception 과 RuntimeException 중에 조상을 선택해 예외 생성
class 예외1 extends Exception {
    생성자1(String 매개변수1) { // 문자열을 매개변수도 받는 생성자
        super(매개변수1); // Exception 클래스의 생성자 호출
    }
}
```

## 예외 되던지기(exception re-throwing)

예외 처리 후 다시 예외 발생시키는 것

```java 
// 호출한 메서드와 호출된 메서드 양쪽 모두에서 예외 처리
class 클래스1 {
    public static void main(String[] args) {
        try {
            메서드1(); // 예외 발생 > 예외 처리 > 예외 발생
        } catch (Exception e) { // 남아 있는 예외 처리
            System.out.println("main 메서드에서 예외 처리");
        }
    } // main 메서드 끝
    
    static 반환 타입 메서드1() throws Exception {
        try {
            throw new Exception();
        } catch (Exception e) {
            System.out.println("메서드1에서 예외 처리");
            throw e; //다시 예외 발생
        }
    }
}
```

## 연결된 예외(chained exception)

예외가 다른 예외 발생시킬 수 있다

예외 a가 예외 b를 발생시키면 a는 b의 원인 예외(cause exception)

Throwable initCause(Throwable cause) = 지정한 예외를 원인 예외로 등록

Throwable getCause() = 원인 예외 반환

```java
// Throwable 은 Exception 과 error 의 조상
public class Throwable implements Serializable {
    private Throwable cause = this; // 객체 자신을 원인 예외로 등록
    public synchronized Throwable initCause(Throwable cause) {
        this.cause = cause; // cause 를 원인 예외로 등록
        return this;
    }
}
```

### 사용 이유
- 여러 예외를 하나로 묶어 다루기 위해 사용
- checked 예외를 unchecked 예외로 변경할 때

## Object 클래스

모든 클래스의 조상, 11개의 메서드 보유

notify(), wait() 등은 쓰레드와 관련된 메서드

## equals(Object obj)

객체 자신(this)와 주어진 객체(obj)를 비교한다. 같으면 true 다르면 false

Object 클래스의 equals()는 객체의 주소를 비교(참조 변수값 비교)

## equals(Object obj)의 오버라이딩

인스턴스 변수의 값을 비교하도록 equals()를 오버라이딩 해야 한다

```java 
class 클래스1 {
    long 변수1;
    
    public boolean equals(Object obj) {
        if(obj instanceof 클래스1)
            // obj 가 Object 타입이므로 변수1값을 참조하기 위해 클래스1 타입으로 형변환 필요함
            return 변수1 == ((클래스1)obj).변수1;
        else
            // 타입이 클래스1이 아닐경우 비교 할 필요 없음
            return false;
    }
    
    클래스1(long 변수1) {
        this.변수1 = 변수1;
    }
}
```

## hashCode()

객체의 해시코드(hash code)를 반환하는 메서드

Object 클래스의 hashCode()는 객체의 주소를 int 로 변환해서 반환

```java 
public class Object {
    public native int hashCode(); // 내용 없음
}
```

equals()를 오버라이딩하면, hashCode()도 오버라이딩 해야 한다

equals()의 결과가 true 인 두 객체의 해시코드가 같아야 하기 때문이다

## toString(), toString()의 오버라이딩

toString() = 객체를 문자열로 변환하기 위한 메서드

## String 클래스

String 클래스 = 데이터(char[]) + 메서드(문자열 관련)

내용을 변경할 수 없는 불변(immutable) 클래스

덧셈 연산자를 이용한 문자열 결합은 성능이 떨어짐

문자열 결합이나 변경이 잦다면 내용을 변경 가능한 StringBuffer 를 사용

## 문자열의 비교

```java 
// 내용 변경 불가
String str1 = "abc";
String str1 = "abc";

str1 == str2 ? true // 주소값 비교
str1.equals(str2) ? true // 내용 비교

// 매번 새로운 String 인스턴스 생성
Sting str3 = new String("abc");
Sting str4 = new String("abc");

str3 == str4 ? false // 주소값 비교
str3.equals(str4) ? true  / 내용 비교
```

## 문자열 리터럴

프로그램 실행 시 자동 생성(constant pool(상수 저장소)에 저장)

같은 내용의 문자열 리터럴은 하나만 만들어짐

## 빈 문자열("", empty string)

내용이 없는 문자열, 크기가 0인 char 형 배열을 저장하는 문자열

어느 타입이나 크기가 0인 배열 생성 가능

```java 
// 문자(char)와 문자열(str)의 초기화
String s = "";
char c = ' ';
```

## join()과 StringJoiner

join()은 여러 문자열 사이에 구분자를 넣어서 결합

`String 변수1 = String.join("구분자", 배열);`

## 문자열과 기본형 간의 변환

숫자를 문자열로 바꾸는 방법

```java 
int 변수1 = 100;
// 방법 1 = 편리함
String 변수2 = 변수1 + "";
// 방법 2 = 빠름
String 변수3 = String.valueOf(변수1);
```

문자열을 숫자로 바꾸는 방법

```java 
// 방법 1
int 변수1 = Integer.parseInt("100");
// 방법 2 = 원래는 반환 타입이 Integer, 기본형으로 써도 상관 없음
int 변수2 = Integer.valueOf("100"); // 기본형
Integer 변수2 = Integer.valueOf("100"); // 참조형
```

## StringBuffer 클래스

String 처럼 문자형 배열(char[])을 내부적으로 가지고 있다

String 과 달리 내용을 변경할 수 있다

## StringBuffer 의 생성자

배열은 길이 변경 불가, 공간이 부족할 경우 새로 생성

StringBuffer 는 저장할 문자열의 길이를 고려해 적절한 크기로 생성

## StringBuffer 의 변경

String 과 달리 내용 변경 가능

append()는 지정된 내용을 추가 후, StringBuffer 의 참조를 반환

## StringBuffer 의 비교

StringBuffer 는 equals()가 오버라이딩되어 있지 않다

String 으로 변환 후 equals()로 비교해야 한다

## StringBuilder

동기화되지 않았다.

StringBuffer 는 동기화되어 있다 멀티 쓰레드에 안전(thread-safe)

싱글 쓰레드 = 한 번에 1개 작업

멀티 쓰레드 = 한 번에 n 개 작업

멀티 쓰레드 프로그램이 아닌 경우 동기화는 불필요한 성능저하

이럴 때 StringBuffer 대신 StringBuilder 사용하면 성능 향상

StringBuffer 과 메서드 동일, 동기화 여부만 차이

## Math 클래스

수학관련 static 메서드의 집합

인스턴스 생성할 필요 없음

## 래퍼(wrapper) 클래스

기본형 값을 감싸는 클래스

8개의 기본형을 객체로 다뤄야 할 때 사용하는 클래스

## Number 클래스

모든 숫자 래퍼 클래스의 조상

## 문자열을 숫자로 변환하기

### 문자열을 숫자로 변환하는 방법

```java 
// floatValue(), longValue 등
int 변수1 = new Integer("100").intValue();

// 주로 사용
int 변수2 = Integer.parseInt("100");

// Integer 대신 int 가능
Integer 변수3 = Integer.valueOf("100");
```

### n 진법의 문자열을 숫자로 변환하는 방법

```java 
int 변수4 = Integer.parseInt("100", 2); // 100(2) > 4
int 변수5 = Integer.parseInt("100", 8); // 100(8) > 64
int 변수6 = Integer.parseInt("100", 16); // 100(16) > 256
int 변수7 = Integer.parseInt("FF", 16); //  FF(16) > 256
int 변수8 = Integer.parseInt("FF"); // NumberFormatException 발생
```

## 오토박싱 & 언박싱

기본형의 값을 객체로 자동변환하는 것을 오토박싱 그 반대가 언박싱

## 날짜와 시간

### Calendar 클래스

추상 클래스이므로 getInstance()를 통해 구현된 객체를 얻어야 한다

```java 
// 현재 시간
Calendar 변수1 = Calendar.getInstance();

// 특정 필드의 값 가져오기
변수1.get(Calendar.YAER) // 년
        
// 특정 필드의 값 설정하기
변수1.set(1234, 5, 6) // 년, 월, 일
        
// Calendar 의 모든 필드 초기화
// 1970년 1월 1일 00시 00분 00초
변수1.clear()

// 특정 필드의 값 증가 또는 감소, 다른 필드에 영향 있음
// 변수1이 8월 31일일 경우 9월 1일로 변경
변수1.add(Calendar.DATE, +1)

// 특정 필드의 값 증가 또는 감소, 다른 필드에 영향 없음
// 변수1이 8월 31일일 경우 8월 1일로 변경
변수1.roll(Calendar.DATE, -8)
```

### Date 와 Calendar 간의 변환

```java 
// Calendar > Date
Calendar cal = Calendar.getInstance();
Date d = new Date(Calendar.getTimeInMillis());

// Date > Calendar
Date d = new Date();
Calendar cal = Calendar.getInstance();
cal.setTime(d)
```

## 형식화 클래스

java.text 패키지의 DecimalFormat, SimpleDateFormat

숫자 or 날짜 > 원하는 형식 기능

형식 문자열 > 숫자 or 날짜 기능

### DecimalFormat

```java 
// 숫자 or 날짜 > 원하는 형식
double number = 1234567.89;
DecimalFormat df = new DecimalFormat("#.#E0");
String result = df.format(number);
// result = "1.2E6"

// 형식 문자열 > 숫자 or 날짜
DecimalFormat df = new DecimalFormat("#,###.##");
Number num = df.parse("1,234,567.89")
double d = num.doubleValue();
// d = 1234567.89
// Integer.parseInt()는 콤마가 포함된 문자열 숫자로 변환 못함 
```

### SimpleDateFormat

```java 
// 날짜와 시간 다양한 형식으로 출력
Date today = new Date();
SimpleDateFormat df = new SimpleDateFormat("yyyy-MM-dd");
String result = df.format(today);

// 특정 형식으로 되어 있는 문자열에서 날짜와 시간 추출
DateFormat df = new SimpleDateFormat("yyyy년 MM월 dd일");
DataFormat df2 = new SimpleDateFormat("yyyy/MM/dd");
Date d = df.parse("2015년 11월 23일");
String result = df2.format(d);
```

## 컬렉션 프레임웍(collections framework)

컬렉션(collection) = 객체를 모아놓은 것

프레임웍(framework) = 표준화, 정형화된 체계적인 프로그래밍 방식

### 컬렉션 프레임웍(collections framework)

- 컬렉션(다수의 객체)을 다루기 위해 표준화된 프로그래밍 방식
- 컬렉션을 쉽고 편리하게 다룰 수 있는 다양한 클래스 제공

컬렉션 클래스(collection class) = 다수의 데이터를 저장할 수 있는 클래스(Vector, ArrayList, HashSet)

## 컬렉션 프레임웍의 핵심 인터페이스

List = 순서 존재, 중복 허용

Set = 순서 없음, 중복 비허용

Map = 순서 없음, 값만 중복 허용

Collection = List 와 Set 의 공통부분을 뽑아낸 것

## Collection 인터페이스의 메서드

boolean add(Object o), boolean addAll(Collection c) = 추가

boolean remove(Object o) = 삭제

boolean removeAll(Collection c) = 삭제

void clear() = 전체 삭제

boolean isEmpty() = 비어있는지 확인

int size() = 저장된 객체의 개수 반환

boolean contains(Object o), boolean containsAll(Collection c) = 특정 객체를 가지고 있는지 검색

## List 인터페이스 = 저장 순서 유지, 중복 허용

void add(int index, Object element), boolean addAll(int index, Collection c) = 추가

Object remove(int index) = 삭제

Object get(int index) = 읽기

Object set(int index, Object element) = 변경

int indexOf(Object o), int lastIndexOf(Object o) = 검색

void sort(Comparator c) = 정렬

List subList(int fromIndex, int toIndex) = 일부 리스트 추출

## Set 인터페이스 = 저장 순서 없음, 중복 비허용

Collection 인터페이스와 동일한 메서드

## Map 인터페이스 = 저장 순서 없음, 값은 중복 허용

Object put(Object key, Object value), void putAll(Map t) = 추가

Object remove(Object key) = 삭제

boolean containsKey(Object key), boolean containsValue(Object value), Object get(Object key) = 검색

Set entrySet(), Set keySet(), Collection values() = 읽기

## ArrayList

기존의 Vector 를 개선한 것, 구현원리와 기능적으로 동일

ArrayList 와 달리 Vector 는 자체적으로 동기화되어 있다

List 인터페이스를 구현하므로, 저장 순서 유지, 중복 허용

데이터 저장 공간으로 배열 사용

## ArrayList 의 메서드

ArrayList() = 기본 생성자

ArrayList(Collection c), ArrayList(int initialCapacity) = 배열 길이 설정 생성자

boolean add(Object o), boolean addAll(Collection c) = 추가, 성공하면 true, 실패하면 false

void add(int index, Object element), boolean addAll(int index, Collection c) = 저장 위치에 추가

boolean remove(Object o), boolean removeAll(Collection c) = 삭제

Object remove(int index) = 특정 위치 삭제

void clear() = 전체 삭제

int indexOf(Object o), int lastIndexOf(Object o) = 검색

boolean contains(Object o) = 검색, 있으면 true, 없으면 false

Object get(int index) = 특정 위치 객체 반환

Object set(int index, Object element) = 특정 위치 객체 변환

List subList(int fromIndex, toIndex) = fromIndex 와 toIndex 사이에 객체 추출 후 리스트 생성

Object[] toArray() = ArrayList 의 객체 반환

boolean isEmpty() = 비어있는 지 확인

void trimToSize() = 빈 공간 제거

int size() = 저장된 객체 수 반환

## ArrayList 에 저장된 객체의 삭제 과정

### ArrayList 에 저장된 세 번째 데이터를 삭제하는 과정

```java 
// 길이 7의 배열
data1 = [0,1,2,3,4,5,6]

// 세 번째 데이터 아래 데이터를 한 칸씩 위로 복사 후 덮어 쓰기
data1 = [0,1,2,4,5,6,null]

// 데이터 수가 줄어듬에 따라 배열의 크기 감소
data1 = [0,1,2,4,5,6]
```

- 삭제할 데이터 아래의 데이터를 한 칸씩 위로 복사해서 삭제할 데이터를 덮어쓴다
- 데이터가 모두 한 칸씩 이동해 마지막 데이터는 null 로 변경
- 데이터 삭제 후 데이터 개수가 줄었으므로 size 의 값 감소
- 마지막 데이터를 삭제하는 경우 배열의 복사는 불필요

### LinkedList

### 배열의 장단점
- 장점 = 구조 간단, 데이터를 읽는 접근 시간 짧음
- 단점 = 크기 변경 불가, 비순차적인 데이터 추가 및 삭제에 시간이 많이 걸림

배열과 달리 링크드 리스트는 불연속적으로 존재하는 테이블을 연결(link)

데이터 삭제 = 참조 변경

데이터 추가 = Node 객체 생성 후 참조 변경

링크드 리스트(linked list) = 연결 리스트, 데이터 접근성이 나쁨

더블리 링크드 리스트(doubly linked list) = 이중 연결 리스트, 접근성 향상

더블리 서큘러 링크드 리스트(doubly circular linked list) = 이중 원형 연결 리스트

순차적으로 데이터 추가 및 삭제 = ArrayList 가 더 빠름

비순차적으로 데이터 추가 및 삭제 = LinkedList 가 더 빠름

접근시간 = ArrayList

## 스택과 큐(Stack & Queue)

스택(Stack) = LIFO 구조, 마지막에 저장된 것을 먼저 꺼낸다

큐(Queue) = FIFO 구조, 먼저 저장한 것을 먼저 꺼낸다

스텍 = 배열로 구현하는 것이 좋음

큐 = 링크드리스트로 구현하는 것이 좋음

## 스택과 큐(Stack & Queue)의 메서드

### 스택의 메서드
boolean empty() = 스택이 비어있는지 알려준다

Object pop() = 삭제

Object push(Object item) = 추가

Object peek() = 맨 위에 저장된 객체 반환

int search(Object o) = 객체를 찾아 위치 반환, 없으면 -1

### 큐의 메서드

boolean offer(Object o) = 추가, 성공하면 true 실패하면 false

Object poll() = 삭제, 비어있으면 null 반환

Object remove() = 삭제, 비어있으면 예외 발생

boolean add(Object o) = 추가, 실패하면 예외 발생

## Iterator, ListIterator, Enumeration

컬렉션에 저장된 데이터를 접근하는 데 사용되는 인터페이스

boolean hasNext() = 읽어올 요소가 있는지 확인, 있으면 true 없으면 false

Object next() = 다음 요소를 읽어 온다

컬렉션에 저장된 요소들을 읽어오는 방법을 표준화한 것

컬렉션에 iterator()를 호출해서 Iterator 를 구현한 객체를 얻어서 사용

```java 
List list = new ArrayList();
Iterator it = list.iterator();

while(it.hasNext()) {
    System.out.println(it.next());
}
```

## Map 과 Iterator

Map 에는 iterator 가 없다, keySet(), entrySet(), values() 호출해야 함

## Arrays

배열의 출력 = toString()

배열의 복사 = copyOf(), copyOfRange()

배열 채우기 = fill(), setAll()

배열의 정렬과 검색 = sort(), binarySearch() //정렬된 배열에 사용

### 순차 검색과 이진 검색
- 순차 검색 = 순서대로 찾는 것
- 이진 탐색 = 둘로 나눠서 찾는 것

다차원 배열의 출력 = deppToString()

다차원 배열의 비교 = deepEquals)

배열을 리스트로 변환 = asList()

람다와 스트림 관련 = parallelXXX(), spliterator(), stream()

## Comparator 와 Comparable

객체 정렬에 필요한 메서드(정렬 기준 제공)를 정의한 인터페이스

Comparable = 기본 정렬 기준 구현에 사용

Comparator = 기본 정렬 기준 외 다른 기준으로 정렬할 때 사용

compare()과 compareTo()는 두 객체의 비교결과를 반환하도록 작성

