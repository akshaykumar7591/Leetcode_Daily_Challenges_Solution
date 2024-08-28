class Solution {

    // Directions in which we can traverse inside the grids.
    private final int[][] directions = {
        { 0, 1 },
        { 1, 0 },
        { 0, -1 },
        { -1, 0 },
    };

    // Helper method to check if the cell at the position (x, y) in the 'grid'
    // is a land cell.
    private boolean isCellLand(int x, int y, int[][] grid) {
        return grid[x][y] == 1;
    }

    // Traverse all cells of island starting at position (x, y) in 'grid2',
    // and check this island is a sub-island in 'grid1'.
    private boolean isSubIsland(
        int x,
        int y,
        int[][] grid1,
        int[][] grid2,
        boolean[][] visited
    ) {
        int totalRows = grid2.length;
        int totalCols = grid2[0].length;

        boolean isSubIsland = true;

        Queue<int[]> pendingCells = new LinkedList<>();
        // Push the starting cell in the queue and mark it as visited.
        pendingCells.offer(new int[] { x, y });
        visited[x][y] = true;

        // Traverse on all cells using the breadth-first search method.
        while (!pendingCells.isEmpty()) {
            int[] curr = pendingCells.poll();
            int currX = curr[0];
            int currY = curr[1];

            // If the current position cell is not a land cell in 'grid1',
            // then the current island can't be a sub-island.
            if (!isCellLand(currX, currY, grid1)) {
                isSubIsland = false;
            }

            for (int[] direction : directions) {
                int nextX = currX + direction[0];
                int nextY = currY + direction[1];
                // If the next cell is inside 'grid2', is never visited and
                // is a land cell, then we traverse to the next cell.
                if (
                    nextX >= 0 &&
                    nextY >= 0 &&
                    nextX < totalRows &&
                    nextY < totalCols &&
                    !visited[nextX][nextY] &&
                    isCellLand(nextX, nextY, grid2)
                ) {
                    // Push the next cell in the queue and mark it as visited.
                    pendingCells.offer(new int[] { nextX, nextY });
                    visited[nextX][nextY] = true;
                }
            }
        }

        return isSubIsland;
    }

    public int countSubIslands(int[][] grid1, int[][] grid2) {
        int totalRows = grid2.length;
        int totalCols = grid2[0].length;

        boolean[][] visited = new boolean[totalRows][totalCols];
        int subIslandCounts = 0;

        // Iterate on each cell in 'grid2'
        for (int x = 0; x < totalRows; ++x) {
            for (int y = 0; y < totalCols; ++y) {
                // If cell at the position (x, y) in the 'grid2' is not visited,
                // is a land cell in 'grid2', and the island
                // starting from this cell is a sub-island in 'grid1', then we
                // increment the count of sub-islands.
                if (
                    !visited[x][y] &&
                    isCellLand(x, y, grid2) &&
                    isSubIsland(x, y, grid1, grid2, visited)
                ) {
                    subIslandCounts += 1;
                }
            }
        }
        // Return total count of sub-islands.
        return subIslandCounts;
    }
}
