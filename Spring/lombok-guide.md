# How To Use Lombok

## 롬복 사용 방법 (IntelliJ)
인텔리제이는 별도의 설치 없이 인텔리제이의 플러그인을 이용하여 롬복을 사용할 수 있다.

### 1. 플러그인 설치
File → Settings → Plugins → Marketplace → Plugins → lombok 검색
인텔리제이 최신 버전을 이용하면 기본적으로 Lombok이 설치되어있다.

### 2. Dependency 설정
Gradle을 기준으로, build.gradle 파일의 dependencies 부분에 다음 구문을 추가해준다.
```
dependencies {
	compileOnly 'org.projectlombok:lombok'
	annotationProcessor 'org.projectlombok:lombok'
}
```

### 3. Lombok 어노테이션 처리 활성화
File > Settings > Build, Execution, Deployment > Compiler > Annotation Processors 로 이동하여 Enable annotation processing을 활성화해준다.

위의 과정을 거쳐 IntellJ의 스프링에서 롬복을 사용할 수 있게 된다.