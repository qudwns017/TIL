# DFS(Depth First Search, 깊이 우선 탐색)
> 현재 탐색하고 있는 경로의 끝까지 탐색한 뒤, 다른 경로를 탐색하는 알고리즘

## Map과 재귀를 이용한 DFS 알고리즘 구현
```java
public class DFS {
    static Map<Integer, List<Integer>> graph = new HashMap<>();
    static Map<Integer, Boolean> visited = new HashMap<>(); // 방문한 정점을 저장할 Map 자료구조

    public static void makeGraph() {
        graph.put(0, Arrays.asList(1, 3, 6));
        graph.put(1, Arrays.asList(0, 3));
        graph.put(2, Arrays.asList(3));
        graph.put(3, Arrays.asList(0, 1, 2, 7));
        graph.put(4, Arrays.asList(5));
        graph.put(5, Arrays.asList(4, 6, 7));
        graph.put(6, Arrays.asList(0, 5));
        graph.put(7, Arrays.asList(3, 5));
    }

    public static void dfs(int currentVertex) {
        visited.put(currentVertex, true); // 방문한 정점에 대하여 visited 맵에 true로 추가함
        for (int nextVertex : graph.get(currentVertex)) { // 그래프에서 탐색할 정점과 연결 되어있는 정점들을 차례로 가져옴
            if (!visited.get(currentVertex)) { // 해당 정점에 접근한 적이 없다면
                dfs(nextVertex); // 다음 정점에 대하여 dfs를 다시 실행한다.
            }
        }
    }

    public static void main(String[] args) {
        makeGraph(); // 탐색할 그래프 생성
        dfs(0); // startVertex를 0으로 지정하고 DFS 알고리즘 실행
    }
}
```