class Solution {

    public int[][] validArrangement(int[][] pairs) {
        Map<Integer, Deque<Integer>> adjacencyMatrix = new HashMap<>();
        Map<Integer, Integer> inDegree = new HashMap<>();
        Map<Integer, Integer> outDegree = new HashMap<>();

        // Build the adjacency list and track in-degrees and out-degrees
        for (int[] pair : pairs) {
            int start = pair[0], end = pair[1];
            adjacencyMatrix
                .computeIfAbsent(start, k -> new ArrayDeque<>())
                .add(end);
            outDegree.put(start, outDegree.getOrDefault(start, 0) + 1);
            inDegree.put(end, inDegree.getOrDefault(end, 0) + 1);
        }

        List<Integer> result = new ArrayList<>();

        // Find the start node (outDegree == inDegree + 1)
        int startNode = -1;
        for (int node : outDegree.keySet()) {
            if (outDegree.get(node) == inDegree.getOrDefault(node, 0) + 1) {
                startNode = node;
                break;
            }
        }

        // If no such node exists, start from the first pair's first element
        if (startNode == -1) {
            startNode = pairs[0][0];
        }

        // Start DFS traversal
        visit(startNode, adjacencyMatrix, result);

        // Reverse the result since DFS gives us the path in reverse
        Collections.reverse(result);

        // Construct the result pairs
        int[][] pairedResult = new int[result.size() - 1][2];
        for (int i = 1; i < result.size(); i++) {
            pairedResult[i - 1] = new int[] {
                result.get(i - 1),
                result.get(i),
            };
        }

        return pairedResult;
    }

    private void visit(
        int node,
        Map<Integer, Deque<Integer>> adjMatrix,
        List<Integer> res
    ) {
        Deque<Integer> neighbors = adjMatrix.get(node);
        while (neighbors != null && !neighbors.isEmpty()) {
            int nextNode = neighbors.pollFirst();
            visit(nextNode, adjMatrix, res);
        }
        res.add(node);
    }
}
