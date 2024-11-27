class Solution {

    // Recursive function to find the minimum distance from the current node to
    // the destination node (n-1)
    private int findMinDistance(
        List<List<Integer>> adjList,
        int n,
        int currentNode,
        int[] dp
    ) {
        // We've reached the destination node
        if (currentNode == n - 1) return 0;

        // If this node has already been computed, return the stored value
        if (dp[currentNode] != -1) return dp[currentNode];

        int minDistance = n;

        for (int neighbor : adjList.get(currentNode)) {
            // Recursively find the minimum distance from the neighbor to the destination
            minDistance = Math.min(
                minDistance,
                findMinDistance(adjList, n, neighbor, dp) + 1
            );
        }

        // Store the computed minimum distance in the dp array and return it
        return dp[currentNode] = minDistance;
    }

    public int[] shortestDistanceAfterQueries(int n, int[][] queries) {
        int[] dp = new int[n];
        for (int i = 0; i < n; i++) {
            dp[i] = -1; // DP array to store minimum distances from each node
        }
        List<List<Integer>> adjList = new ArrayList<>(n);

        // Initialize the graph with edges between consecutive nodes
        for (int i = 0; i < n; i++) {
            adjList.add(new ArrayList<>()); // Create a new list for each node
        }
        for (int i = 0; i < n - 1; i++) {
            adjList.get(i).add(i + 1);
        }

        List<Integer> answer = new ArrayList<>();

        // Process each query to add new edges
        for (int[] road : queries) {
            int u = road[0];
            int v = road[1];

            // Add the directed edge from u to v
            adjList.get(u).add(v);

            // Find the minimum distance from the starting node (0) to the destination (n-1)
            answer.add(findMinDistance(adjList, n, 0, dp));

            // Clear and reset the dp array
            for (int i = 0; i < n; i++) {
                dp[i] = -1;
            }
        }

        // Convert List<Integer> to int[] before returning
        int[] result = new int[answer.size()];
        for (int i = 0; i < answer.size(); i++) {
            result[i] = answer.get(i);
        }

        return result; // Return the results for each query
    }
}
