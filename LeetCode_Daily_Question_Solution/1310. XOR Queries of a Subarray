class Solution {

    public int[] xorQueries(int[] arr, int[][] queries) {
        int[] result = new int[queries.length];
        // Process each query
        for (int i = 0; i < queries.length; i++) {
            int xorSum = 0;
            // Calculate XOR for the range [q[0], q[1]]
            for (int j = queries[i][0]; j <= queries[i][1]; j++) {
                xorSum ^= arr[j];
            }
            result[i] = xorSum;
        }
        return result;
    }
}
