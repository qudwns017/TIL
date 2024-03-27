# REST API(Representational State Transfer, 자원의 상태 전달)

## 네트워크 아키텍처 원리

### Client, Server

- 클라이언트와 서버가 서로 독립적으로 분리되어져 있어야 한다.

### Stateless

- 요청에 대해서 서버는 클라이언트가 요청한 정보를 저장하지 않는다.

### 캐시

- 클라이언트는 서버의 응답을 캐시 할 수 있어야 한다.
- 클라이언트가 캐시를 통해서 응답을 재사용할 수 있어야 하며, 이를 통해 서버의 부하를 낮춘다.

### 계층화

- 서버와 클라이언트 사이에 방화벽, 게이트웨이, Proxy 등 다계층 형태를 구성할 수 있어야 하며 확장할 수 있어야 한다.

### 인터페이스 일관성

- 아키텍처를 단순화시키고 작은 단위로 분리하여서, 클라이언트 및 서버가 독립적으로 개선될 수 있어야 한다.

1. **자원 식별** : 웹 기반의 REST에서는 리소스 접근을 URI를 통해 사용
2. **메시지를 통한 리소스 조작** : Header 부분에 content-type을 통해 어떠한 리소스 타입인지 지정 가능
3. **자기서술적 메세지** : HTTP Method와 Header의 정보와 같은 수단으로 요청하는 데이터가 어떻게 처리 되어져야 하는지 나타내야 함
4. **애플리케이션 상태에 대한 엔진으로서 하이퍼미디어** : 단순히 클라이언트의 요청에 대한 데이터만 내리는 것이 아닌, 관련된 리소스에 대한 Link 정보까지 같이 포함 되어야 함

### Code On Demand

- 자바 애플릿, 자바스크립트 플래시 등 특정기능을 서버가 클라이언트에 코드를 전달하여 실행 할 수 있어야 한다.