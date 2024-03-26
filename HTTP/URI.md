# URI(Uniform Resource Identifier)

> 인터넷에서 특정 자원을 나타내는 주소값. 해당 값은 유일하다.<br>
> ex : https://www.foo.co.kr/resource/sample/**1** 에서 1과 같은 존재

## URL(Uniform Resource Locator)

> 인터넷 상에서의 자원, 특정 파일이 어디에 위치하는지 식별 하는 주소<br>
> URL은 URI의 하위 개념<br>
> ex : https://www.foo.co.kr/**sample1.pdf** 에서 sample1.pdf 부분

## URI 설계 원칙(RFC-3986)

|                              원칙                               |                                                              예시                                                               |
| :-------------------------------------------------------------: | :-----------------------------------------------------------------------------------------------------------------------------: |
|          슬래시(/) 는 계층 관계를 나타내는데 사용한다.          |                                                https://foo.co.kr/vehicles/suv/q6                                                |
|         URI 마지막 문자로 슬래시(/)는 포함하지 않는다.          |                                             https://foo.co.kr/vehicles/suv/q6/ (X)                                              |
|         하이픈(-)은 URI 가독성을 높이는 데에 사용한다.          |                                          https://foo.co.kr/vehicles/suv/**q-series**/6                                          |
|                   밑줄(\_)은 사용하지 않는다.                   |                                        https://foo.co.kr/vehicles/suv/**q_series**/6 (X)                                        |
|                 URI 경로에는 소문자가 적합하다.                 |                                              https://Foo.co.kr/Vehicles/SUB/Q6 (X)                                              |
|              파일 확장자는 URI에 포함하지 않는다.               |                                          https://foo.co.kr/vehicles/suv/q6**.jsp** (X)                                          |
|      프로그래밍 언어에 의존적인 확장자를 사용하지 않는다.       |                                          https://foo.co.kr/vehicles/suv/q6.**do** (X)                                           |
|             구현에 의존적인 경로를 사용하지 않는다.             |                                       https://foo.co.kr/**servelet**/vehicles/suv/q6 (X)                                        |
|                   세션 ID를 포함하지 않는다.                    |                                     https://foo.co.kr/vehicles/suv/q6?session-id=abcdef (X)                                     |
|          프로그래밍 언어의 Method명을 이용하지 않는다.          |                                         https://foo.co.kr/vehicles/suv/q6?action=intro                                          |
|          명사에 단수형 보다는 복수형을 사용해야 한다.           |                                              https://foo.co.kr/vehicle/suv/q6 (X)                                               |
|          컨트롤러 이름으로는 동사나 동사구를 사용한다.          |                                         https://foo.co.kr/vehicles/suv/q6/re-order (O)                                          |
|       경로 부분 중 변하는 부분은 유일한 값으로 대체 한다.       | https://foo.co.kr/vehicles/suv/q6/{car-id}/users/{user-id}/release<br>https://foo.co.kr/vehicles/suv/q6/117/users/steve/release |
|        CRUD 기능을 나타내는 것은 URI에 사용하지 않는다.         |            https://foo.co.kr/vehicles/suv/q6/delete/{car-id}/ (X)<br>https://foo.co.kr/vehicles/suv/q6/{car-id}/ (O)            |
| URI Query Prameter 디자인<br>필터링이나 페이지로 나타날 때 유용 |               https://foo.co.kr/vehicles/suv?model=q7<br> https://foo.co.kr/vehicles/suv?page=0&size=10&sort=asc                |
|      API에 있어서 서브 도메인은 일관성 있게 사용해야 한다.      |                                           https://foo.co.kr<br>https://api.foo.co.kr                                            |
|    클라이언트 개발자 포탈 서브 도메인은 일관성 있게 만든다.     |                                  https://dev-api.foo.co.kr<br>https://developer-api.foo.co.kr                                   |
