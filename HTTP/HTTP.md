# HTTP (Hyper Text Transfer Protocol)

> RFC 2616에서 규정된 Web에서 데이터를 주고 받는 **프로토콜**<br>
> 프로토콜 뿐만 아니라 HTML, XML, JSON, Image, Javascript 등 컴퓨터에서 다룰 수 있는 모든 것은 전송 가능<br>
> HTTP는 TCP를 기반으로 한 REST의 특징을 모두 구현하고 있는 Web 기반의 프로토콜

## HTTP 메서드들의 의미 및 특성

| 메서드 |       의미        | CRUD  | 멱등성 | 안정성 | Path Variable | Query Parameter | DataBody |
| :----: | :---------------: | :---: | :----: | :----: | :-----------: | :-------------: | :------: |
|  GET   |    리소스 취득    |   R   |   O    |   O    |       O       |        O        |    X     |
|  POST  | 리소스 생성, 추가 |   C   |   X    |   X    |       O       |        △        |    O     |
|  PUT   | 리소스 갱신, 생성 | C / U |   O    |   X    |       O       |        △        |    O     |
| DELETE |    리소스 삭제    |   D   |   O    |   X    |       O       |        O        |    X     |


