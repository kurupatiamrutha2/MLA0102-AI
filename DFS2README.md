graph = {
    1: [2, 3],
    2: [1, 5, 6],
    3: [1, 7, 4],
    4: [3, 8],
    5: [2],
    6: [2],
    7: [3, 8],
    8: [7, 4]
}

def dfs(start, visited=None):
    if visited is None:
        visited = []

    visited.append(start)
    print(start, end=" ")

    for neighbor in graph[start]:
        if neighbor not in visited:
            dfs(neighbor, visited)

# Run DFS
print("DFS Traversal:", end=" ")
dfs(1)
