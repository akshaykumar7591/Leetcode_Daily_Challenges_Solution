class Solution {

    public boolean[] isArraySpecial(int[] nums, int[][] queries) {
        int n = nums.length;
        int[] maxReach = new int[n];
        int end = 0;

        // Step 1: Compute the maximum reachable index for each starting index
        for (int start = 0; start < n; start++) {
            // Ensure 'end' always starts from the current index or beyond
            end = Math.max(end, start);

            // Expand 'end' as long as adjacent elements have different parity
            while (end < n - 1 && nums[end] % 2 != nums[end + 1] % 2) {
                end++;
            }

            // Store the farthest index reachable from 'start'
            maxReach[start] = end;
        }

        boolean[] ans = new boolean[queries.length];

        // Step 2: Answer each query based on precomputed 'maxReach'
        for (int i = 0; i < queries.length; i++) {
            int start = queries[i][0];
            int endQuery = queries[i][1];

            // Check if the query range [start, end] lies within the max reachable range
            ans[i] = endQuery <= maxReach[start];
        }

        return ans;
    }
}
