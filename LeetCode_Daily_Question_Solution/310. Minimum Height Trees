class Solution {
    public List<Integer> findMinHeightTrees(int n, int[][] edges) {
        if (n == 1) return Collections.singletonList(0);
        
        int[] degree = new int[n];
        Map<Integer, List<Integer>> adjacencyList = new HashMap<>();
        for (int[] edge : edges) {
            degree[edge[0]]++;
            degree[edge[1]]++;
            adjacencyList.computeIfAbsent(edge[0], x -> new ArrayList<>()).add(edge[1]);
            adjacencyList.computeIfAbsent(edge[1], x -> new ArrayList<>()).add(edge[0]);
        }

        Queue<Integer> leaves = new LinkedList<>();
        for (int i = 0; i < degree.length; i++) {
            if (degree[i] == 1) {
                leaves.add(i);
            }
        }

        int remainingNodes = n;
        while (remainingNodes > 2) {
            int size = leaves.size();
            remainingNodes -= size;
            for (int i = 0; i < size; i++) {
                int leaf = leaves.poll();
                for (int neighbor : adjacencyList.get(leaf)) {
                    if (--degree[neighbor] == 1) {
                        leaves.add(neighbor);
                    }
                }
            }
        }

        return new ArrayList<>(leaves);
    }
}
