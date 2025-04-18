# 📘 이찬솔 (202103323)

---

## ✅ 8주차 (4월 18일)

### 1. 객체 속의 `this`

- `this`는 객체 자기 자신을 가리킴
- 객체의 속성 접근
  - `객체명.속성이름`
  - `객체명["속성이름"]`
- 객체의 메서드 호출
  - `객체명.메서드이름()`

```javascript
let person = {
  name: "홍길동",
  cm: 180,
  kg: 80,
  birthday: "681212",
  id: "123456",
  uId: function() {
    return this.birthday + "-" + this.id;
  }
};
```

---

### 2. 객체 반복 (`for...in`, `for...of`)

- `for...in`: 객체의 key를 반복
```javascript
for (let key in person) {
  console.log(key + " : " + person[key]);
}
```

---

### 3. 생성자 함수로 객체 만들기

```javascript
function Person(name, cm, kg, addr, age) {
  this.name = name;
  this.cm = cm;
  this.kg = kg;
  this.addr = addr;
  this.age = age;
}
```

---

## ✅ 상속 (Inheritance)

- 부모 객체의 속성과 메서드를 자식 객체가 물려받음

### 장점
- 코드 재사용성
- 유지보수 용이

### 업캐스팅 예시
```java
Person[] people = new Person[3];
people[0] = new Student("홍길동");
people[1] = new Student("김영희");
people[2] = new Person("이순신");
```

---

## ✅ 매개변수와 전달인자

- **매개변수(Parameter)**: 함수 정의 시 변수
- **전달인자(Argument)**: 함수 호출 시 넘기는 값

```python
def plus(a, b):  # a, b는 매개변수
  return a + b

result = plus(1, 2)  # 1, 2는 전달인자
```

---

## ✅ 생성자 개념

### 1. 기본 생성자
- 매개변수가 없음

### 2. 매개변수 생성자
- 값을 전달받아 초기화

### 3. 복사 생성자
- 다른 객체를 복사

### 4. this() vs this
- `this()`는 생성자 호출
- `this`는 인스턴스 자신을 가리킴

```java
class Person {
  String name;
  int age;

  public Person() {
    this.name = "이름 없음";
    this.age = 0;
  }

  public Person(String name, int age) {
    this.name = name;
    this.age = age;
  }

  public Person(Person other) {
    this.name = other.name;
    this.age = other.age;
  }

  public void displayInfo() {
    System.out.println("이름: " + name + ", 나이: " + age);
  }
}
```

---

## ✅ 객체 소멸자와 가비지 컬렉터

- 참조되지 않는 객체는 GC가 자동 소멸
- `finalize()` 오버라이드 가능

```java
@Override
protected void finalize() throws Throwable {
  System.out.println("객체 소멸 직전 실행됨");
}
```

---

## ✅ 비트 연산자 요약

| 연산자 | 설명                  |
|--------|-----------------------|
| ~      | 비트 반전             |
| &      | 논리곱                |
| \|     | 논리합                |
| ^      | 배타적 논리합 (XOR)   |
| <<     | 왼쪽 시프트 (곱셈 효과) |
| >>     | 오른쪽 시프트 (나눗셈 효과) |
| >>>    | 오른쪽 0 채우기       |

---

## ✅ 자바 개요 및 기초

### 1. 플랫폼 독립성
- Write Once, Run Anywhere

### 2. 객체지향 프로그래밍(OOP)의 핵심
- 클래스, 객체, 인스턴스, 상속 등

### 3. 캡슐화 (Encapsulation)
- 객체의 내부 구조를 외부에 숨기고, 필요한 정보만 제공

---

## ✅ 코드 예제 모음

```java
// 원의 면적 계산 예제
public class Bar {
    public static void main(String[] args) {
        final double PI = 3.14;
        double radius = 10.2;
        double circleArea = radius * radius * PI;
        System.out.print("반지름 " + radius + ", ");
        System.out.println("원의 면적 = " + circleArea);
    }
}
```

---

## ✅ 용어 정리

| 용어        | 의미 |
|-------------|------|
| 식별자       | 변수, 함수, 클래스 이름 등 |
| 참조형       | 객체, 배열, String 등 |
| Object       | 모든 클래스의 조상 클래스 |
| String       | char 배열로 구성된 참조형 자료 |
| Class        | 객체의 설계도 |
| Instance     | 클래스에서 생성된 실제 객체 |
| Constructor  | 객체를 생성할 때 호출되는 메서드 |
