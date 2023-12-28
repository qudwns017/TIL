# 자바 가상 머신(Java Virtual Machine, JVM)

## 자바 가상 머신이란?
JVM의 역할은 자바 애플리케이션을 클래스 로더를 통해 읽어 들여 자바 API와 함께 실행하는 것이다.

## 특징
1. 운영체제(OS)에 구애 받지 않는 독립적인 개발이 가능하다. (JAVA - OS 사이의 중개자 역할)
2. 컴파일된 바이트 코드를 기계가 이해할 수 있는 기계어로 변환
3. 스택 기반의 가상 머신
4. 메모리 관리와 GC를 수행

## JVM를 이용한 자바의 구동 방식
1. JDK를 통한 코드(.java / javac.exe / .class) 파일 작성
2. 실행을 하면 JVM 호출
3. JVM의 Class Loader를 통해 클래스 파일을 Runtime Data Area의 메서드 영역으로 불러옴
4. 불려온 클래스는 Execution Engine을 통해 클래스 파일의 ByteCode를 실행 가능케 해석
5. 클래스의 데이터들은 Runtime Data Area에 각 역할 별로 메모리에 저장
6. Runtime Data Area는 Method Area, Heap Area, Stack Area, Runtime Constant Pool 이 4개의 메모리 영역으로 이루어져 있음

