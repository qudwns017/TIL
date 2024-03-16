# Static
## main 클래스가 동작되는 방식
```java
public class Test{
    public static void main(string[] args) {
        System.out.println("Hello, World");
    }
}
```

1. JVM(Java Virtual Machine)이 실행할 클래스를 찾는다.
2. static 키워드가 붙어있는 멤버들을 정해진 메모리 위치, 즉 static-zone에 한 번 자동으로 로딩한다.
   - static 멤버들은 클래스를 사용하는 시점에서 딱 한 번만 메모리에 로딩된다는 점이 중요.
3. JVM이 static-zone에서 main() 메서드를 호출한다.
4. 호출된 메서드를 Stack Area에 push 한 뒤 동작을 시작한다.