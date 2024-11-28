public class Solution {

    // Directions for movement: right, left, down, up
    private final int[][] directions = {
        { 0, 1 },
        { 0, -1 },
        { 1, 0 },
        { -1, 0 },
    };

    public int minimumObstacles(int[][] grid) {
        int m = grid.length, n = grid[0].length;

        int[][] minObstacles = new int[m][n];

        // Initialize all cells with a large value, representing unvisited cells
        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                minObstacles[i][j] = Integer.MAX_VALUE;
            }
        }

        // Start from the top-left corner, accounting for its obstacle value
        minObstacles[0][0] = grid[0][0];

        PriorityQueue<int[]> pq = new PriorityQueue<>((a, b) -> a[0] - b[0]);

        // Add the starting cell to the priority queue
        pq.add(new int[] { minObstacles[0][0], 0, 0 });

        while (!pq.isEmpty()) {
            // Process the cell with the fewest obstacles removed so far
            int[] current = pq.poll();
            int obstacles = current[0], row = current[1], col = current[2];

            // If we've reached the bottom-right corner, return the result
            if (row == m - 1 && col == n - 1) {
                return obstacles;
            }

            // Explore all four possible directions from the current cell
            for (int[] dir : directions) {
                int newRow = row + dir[0], newCol = col + dir[1];

                if (isValid(grid, newRow, newCol)) {
                    // Calculate the obstacles removed if moving to the new cell
                    int newObstacles = obstacles + grid[newRow][newCol];

                    // Update if we've found a path with fewer obstacles to the new cell
                    if (newObstacles < minObstacles[newRow][newCol]) {
                        minObstacles[newRow][newCol] = newObstacles;
                        pq.add(new int[] { newObstacles, newRow, newCol });
                    }
                }
            }
        }

        return minObstacles[m - 1][n - 1];
    }

    // Helper method to check if the cell is within the grid bounds
    private boolean isValid(int[][] grid, int row, int col) {
        return (
            row >= 0 && col >= 0 && row < grid.length && col < grid[0].length
        );
    }
}
