class Solution {

    private static final int MOD = 1000000007;

    public int[] productQueries(int n, int[][] queries) {
        List<Integer> bins = new ArrayList<>();
        int rep = 1;
        while (n > 0) {
            if (n % 2 == 1) {
                bins.add(rep);
            }
            n /= 2;
            rep *= 2;
        }

        int m = bins.size();
        int[][] results = new int[m][m];
        for (int i = 0; i < m; i++) {
            long cur = 1;
            for (int j = i; j < m; j++) {
                cur = (cur * bins.get(j)) % MOD;
                results[i][j] = (int) cur;
            }
        }

        int[] ans = new int[queries.length];
        for (int i = 0; i < queries.length; i++) {
            ans[i] = results[queries[i][0]][queries[i][1]];
        }
        return ans;
    }
}
