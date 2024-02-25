## 메소드란?
- 자바의 클래스는 속성을 표현하는 필드(field)와 기능을 표현하는 메소드(method)를 가짐
- 그 중 메소드(method)란 어떠한 특정 작업을 수행하기 위한 명령문의 집합
## 기본 형태
### 접근 제한자 / 반환 타입 / 메소드명 (매개변수)<br>
ex) public void setName(int Name)

## 자바 메소드의 특징
* 자바에서 메소드는 클래스 안에서만 선언할 수 있다.
```java
class Person {
    public void eat() {
        System.out.println("짜장면 맛있습니다.");
    }
}
```