# BFS (Breadth First Search, 깊이 우선 탐색)
> 맹목적 탐색 방법 중 하나로, 시작 정점을 방문한 후 인접한 모든 정점들을 차례로 방문해서 탐색하는 알고리즘.<br>
> 그래프에 존재하는 모든 정점들에 방문해야만 알고리즘이 종료된다.

## Map과 Queue를 이용한 BFS 구현 방법
```java
public class BFS {
    static Map<Integer, List<Integer>> graph = new HashMap<>();
    static Map<Integer, Boolean> visited = new HashMap<>();

    private static void makeGraph() {
        graph.put(0, Arrays.asList(1, 3, 6));
        graph.put(1, Arrays.asList(0, 3));
        graph.put(2, Arrays.asList(3));
        graph.put(3, Arrays.asList(0, 1, 2, 7));
        graph.put(4, Arrays.asList(5));
        graph.put(5, Arrays.asList(4, 6, 7));
        graph.put(6, Arrays.asList(0, 5));
        graph.put(7, Arrays.asList(3, 5));
    }

    private static void BFS() {
        Queue<Integer> queue = new LinkedList<>(); // 다음 작업을 저장할 큐 생성
        queue.offer(0); // 큐에 시작 정점 추가

        while(!queue.isEmpty()) { // 큐가 empty라는 것은 모든 탐색을 끝낸 경우라는 것을 의미
            int curVertex = queue.poll(); // 탐색할 정점을 변수에 저장
            for (int nextVertex : graph.get(curVertex)) { // 그래프에서 탐색할 정점과 연결 되어있는 정점들을 차례로 가져옴
                if (!visited.containsKey(nextVertex)) { // 해당 정점에 접근한 적이 없다면
                    queue.offer(nextVertex); // 큐에 정점을 추가
                    visited.put(nextVertex, true); // 방문함을 나타내는 visited Map에 정점 value와 true 추가
                }
            }
        }
    }

    public static void main(String[] args) {
        makeGraph(); // 그래프 생성
        BFS(); // BFS 알고리즘 실행
    }
}
```