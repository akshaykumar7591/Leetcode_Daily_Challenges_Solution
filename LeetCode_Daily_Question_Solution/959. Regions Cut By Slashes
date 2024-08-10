class Solution {

    // Directions for traversal: right, left, down, up
    private static final int[][] DIRECTIONS = {
        { 0, 1 },
        { 0, -1 },
        { 1, 0 },
        { -1, 0 },
    };

    public int regionsBySlashes(String[] grid) {
        int gridSize = grid.length;
        // Create a 3x3 matrix for each cell in the original grid
        int[][] expandedGrid = new int[gridSize * 3][gridSize * 3];

        // Populate the expanded grid based on the original grid
        // 1 represents a barrier in the expanded grid
        for (int i = 0; i < gridSize; i++) {
            for (int j = 0; j < gridSize; j++) {
                int baseRow = i * 3;
                int baseCol = j * 3;
                // Check the character in the original grid
                if (grid[i].charAt(j) == '\\') {
                    // Mark diagonal for backslash
                    expandedGrid[baseRow][baseCol] = 1;
                    expandedGrid[baseRow + 1][baseCol + 1] = 1;
                    expandedGrid[baseRow + 2][baseCol + 2] = 1;
                } else if (grid[i].charAt(j) == '/') {
                    // Mark diagonal for forward slash
                    expandedGrid[baseRow][baseCol + 2] = 1;
                    expandedGrid[baseRow + 1][baseCol + 1] = 1;
                    expandedGrid[baseRow + 2][baseCol] = 1;
                }
            }
        }

        int regionCount = 0;
        // Count regions using flood fill
        for (int i = 0; i < gridSize * 3; i++) {
            for (int j = 0; j < gridSize * 3; j++) {
                // If we find an unvisited cell (0), it's a new region
                if (expandedGrid[i][j] == 0) {
                    // Fill that region
                    floodFill(expandedGrid, i, j);
                    regionCount++;
                }
            }
        }
        return regionCount;
    }

    // Flood fill algorithm to mark all cells in a region
    private void floodFill(int[][] expandedGrid, int row, int col) {
        Queue<int[]> queue = new LinkedList<>();
        expandedGrid[row][col] = 1;
        queue.add(new int[] { row, col });

        while (!queue.isEmpty()) {
            int[] currentCell = queue.poll();
            // Check all four directions from the current cell
            for (int[] direction : DIRECTIONS) {
                int newRow = direction[0] + currentCell[0];
                int newCol = direction[1] + currentCell[1];
                // If the new cell is valid and unvisited, mark it and add to queue
                if (isValidCell(expandedGrid, newRow, newCol)) {
                    expandedGrid[newRow][newCol] = 1;
                    queue.add(new int[] { newRow, newCol });
                }
            }
        }
    }

    // Check if a cell is within bounds and unvisited
    private boolean isValidCell(int[][] expandedGrid, int row, int col) {
        int n = expandedGrid.length;
        return (
            row >= 0 &&
            col >= 0 &&
            row < n &&
            col < n &&
            expandedGrid[row][col] == 0
        );
    }
}
