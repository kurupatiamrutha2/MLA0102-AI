from collections import deque

def bfs(graph, start):
    visited = set()
    queue = deque([start])
    visited.add(start)

    bfs_order = []

    while queue:
        node = queue.popleft()
        bfs_order.append(node)

        for neighbor in graph[node]:
            if neighbor not in visited:
                visited.add(neighbor)
                queue.append(neighbor)

    return bfs_order


# Example graph
graph = {
    0: [1],
    1: [2, 3],
    2: [1, 3],
    3: [4],
    4: [5, 6],
    5: [7],
    6: [],
    7: []
}

print("BFS traversal:", bfs(graph, 0))
