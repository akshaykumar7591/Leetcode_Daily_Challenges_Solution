class Solution {

    public int minimumScore(int[] nums, int[][] edges) {
        int n = nums.length;
        List<List<Integer>> adj = new ArrayList<>();
        for (int i = 0; i < n; i++) {
            adj.add(new ArrayList<>());
        }
        for (int[] e : edges) {
            adj.get(e[0]).add(e[1]);
            adj.get(e[1]).add(e[0]);
        }

        int[] sum = new int[n];
        int[] in = new int[n];
        int[] out = new int[n];
        int[] cnt = { 0 };

        dfs(0, -1, nums, adj, sum, in, out, cnt);
        int res = Integer.MAX_VALUE;
        for (int u = 1; u < n; u++) {
            for (int v = u + 1; v < n; v++) {
                if (in[v] > in[u] && in[v] < out[u]) {
                    res = Math.min(
                        res,
                        calc(sum[0] ^ sum[u], sum[u] ^ sum[v], sum[v])
                    );
                } else if (in[u] > in[v] && in[u] < out[v]) {
                    res = Math.min(
                        res,
                        calc(sum[0] ^ sum[v], sum[v] ^ sum[u], sum[u])
                    );
                } else {
                    res = Math.min(
                        res,
                        calc(sum[0] ^ sum[u] ^ sum[v], sum[u], sum[v])
                    );
                }
            }
        }
        return res;
    }

    private int calc(int part1, int part2, int part3) {
        return (
            Math.max(part1, Math.max(part2, part3)) -
            Math.min(part1, Math.min(part2, part3))
        );
    }

    private void dfs(
        int x,
        int fa,
        int[] nums,
        List<List<Integer>> adj,
        int[] sum,
        int[] in,
        int[] out,
        int[] cnt
    ) {
        in[x] = cnt[0]++;
        sum[x] = nums[x];
        for (int y : adj.get(x)) {
            if (y == fa) {
                continue;
            }
            dfs(y, x, nums, adj, sum, in, out, cnt);
            sum[x] ^= sum[y];
        }
        out[x] = cnt[0];
    }
}
