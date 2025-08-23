class Solution {

    private int minimumSum2(int[][] grid, int u, int d, int l, int r) {
        int min_i = grid.length;
        int max_i = 0;
        int min_j = grid[0].length;
        int max_j = 0;
        for (int i = u; i <= d; i++) {
            for (int j = l; j <= r; j++) {
                if (grid[i][j] == 1) {
                    min_i = Math.min(min_i, i);
                    min_j = Math.min(min_j, j);
                    max_i = Math.max(max_i, i);
                    max_j = Math.max(max_j, j);
                }
            }
        }
        return min_i <= max_i
            ? (max_i - min_i + 1) * (max_j - min_j + 1)
            : Integer.MAX_VALUE / 3;
    }

    private int[][] rotate(int[][] vec) {
        int n = vec.length;
        int m = vec[0].length;
        int[][] ret = new int[m][n];
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < m; j++) {
                ret[m - j - 1][i] = vec[i][j];
            }
        }
        return ret;
    }

    private int solve(int[][] grid) {
        int n = grid.length;
        int m = grid[0].length;
        int res = n * m;
        for (int i = 0; i + 1 < n; i++) {
            for (int j = 0; j + 1 < m; j++) {
                res = Math.min(
                    res,
                    minimumSum2(grid, 0, i, 0, m - 1) +
                    minimumSum2(grid, i + 1, n - 1, 0, j) +
                    minimumSum2(grid, i + 1, n - 1, j + 1, m - 1)
                );
                res = Math.min(
                    res,
                    minimumSum2(grid, 0, i, 0, j) +
                    minimumSum2(grid, 0, i, j + 1, m - 1) +
                    minimumSum2(grid, i + 1, n - 1, 0, m - 1)
                );
            }
        }
        for (int i = 0; i + 2 < n; i++) {
            for (int j = i + 1; j + 1 < n; j++) {
                res = Math.min(
                    res,
                    minimumSum2(grid, 0, i, 0, m - 1) +
                    minimumSum2(grid, i + 1, j, 0, m - 1) +
                    minimumSum2(grid, j + 1, n - 1, 0, m - 1)
                );
            }
        }
        return res;
    }

    public int minimumSum(int[][] grid) {
        int[][] rgrid = rotate(grid);
        return Math.min(solve(grid), solve(rgrid));
    }
}
