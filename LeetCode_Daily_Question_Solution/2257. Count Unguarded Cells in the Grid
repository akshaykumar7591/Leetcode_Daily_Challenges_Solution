class Solution {

    private static final int UNGUARDED = 0;
    private static final int GUARDED = 1;
    private static final int GUARD = 2;
    private static final int WALL = 3;

    public void markguarded(int row, int col, int[][] grid) {
        // Traverse upwards
        for (int r = row - 1; r >= 0; r--) {
            if (grid[r][col] == WALL || grid[r][col] == GUARD) break;
            grid[r][col] = GUARDED;
        }
        // Traverse downwards
        for (int r = row + 1; r < grid.length; r++) {
            if (grid[r][col] == WALL || grid[r][col] == GUARD) break;
            grid[r][col] = GUARDED;
        }
        // Traverse leftwards
        for (int c = col - 1; c >= 0; c--) {
            if (grid[row][c] == WALL || grid[row][c] == GUARD) break;
            grid[row][c] = GUARDED;
        }
        // Traverse rightwards
        for (int c = col + 1; c < grid[0].length; c++) {
            if (grid[row][c] == WALL || grid[row][c] == GUARD) break;
            grid[row][c] = GUARDED;
        }
    }

    public int countUnguarded(int m, int n, int[][] guards, int[][] walls) {
        int[][] grid = new int[m][n];

        // Mark guards' positions
        for (int[] guard : guards) {
            grid[guard[0]][guard[1]] = GUARD;
        }

        // Mark walls' positions
        for (int[] wall : walls) {
            grid[wall[0]][wall[1]] = WALL;
        }

        // Mark cells as guarded by traversing from each guard
        for (int[] guard : guards) {
            markguarded(guard[0], guard[1], grid);
        }

        // Count unguarded cells
        int count = 0;
        for (int[] row : grid) {
            for (int cell : row) {
                if (cell == UNGUARDED) count++;
            }
        }
        return count;
    }
}
