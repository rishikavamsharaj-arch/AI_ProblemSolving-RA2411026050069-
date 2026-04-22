import random
from collections import deque

class SmartNavigationSystem:
    def __init__(self, graph):
        self.graph = graph

    def bfs_find_path(self, start, goal):
        """BFS - Guaranteed to find ONE OF the shortest paths."""
        queue = deque([[start]])
        visited = set([start])

        while queue:
            path = queue.popleft()
            node = path[-1]

            if node == goal:
                return path
            neighbors = list(self.graph.get(node, []))
            random.shuffle(neighbors) 

            for adjacent in neighbors:
                if adjacent not in visited:
                    visited.add(adjacent)
                    new_path = list(path)
                    new_path.append(adjacent)
                    queue.append(new_path)
        return None

    def dfs_find_path(self, start, goal):
        """DFS - Will find a random valid path (often not the shortest)."""
        stack = [[start]]
        visited = set()

        while stack:
            path = stack.pop()
            node = path[-1]

            if node == goal:
                return path

            if node not in visited:
                visited.add(node)
                
                neighbors = list(self.graph.get(node, []))
                random.shuffle(neighbors)
                
                for adjacent in neighbors:
                    if adjacent not in visited:
                        new_path = list(path)
                        new_path.append(adjacent)
                        stack.append(new_path)
        return None

if __name__ == "__main__":

    city_map = {
        'Start': ['A', 'B', 'F'],
        'A': ['Start', 'C', 'D'],
        'B': ['Start', 'E', 'C'],
        'C': ['A', 'B', 'Goal', 'F'],
        'D': ['A', 'Goal'],
        'E': ['B', 'Goal'],
        'F': ['Start', 'C', 'Goal'],
        'Goal': ['C', 'D', 'E', 'F']
    }

    nav_system = SmartNavigationSystem(city_map)
    start_location = 'Start'
    destination = 'Goal'

    print("=== Randomized Navigation System ===")
    
    bfs_result = nav_system.bfs_find_path(start_location, destination)
    print("\nBreadth-First Search (BFS) Route:")
    print(" -> ".join(bfs_result))

    dfs_result = nav_system.dfs_find_path(start_location, destination)
    print("\nDepth-First Search (DFS) Route:")
    print(" -> ".join(dfs_result))
