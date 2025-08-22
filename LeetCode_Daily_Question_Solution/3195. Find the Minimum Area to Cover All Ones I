class Solution {

    public int minimumArea(int[][] grid) {
        int n = grid.length;
        int m = grid[0].length;
        int min_i = n;
        int max_i = 0;
        int min_j = m;
        int max_j = 0;
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < m; j++) {
                if (grid[i][j] == 1) {
                    min_i = Math.min(min_i, i);
                    max_i = Math.max(max_i, i);
                    min_j = Math.min(min_j, j);
                    max_j = Math.max(max_j, j);
                }
            }
        }
        return (max_i - min_i + 1) * (max_j - min_j + 1);
    }
}
