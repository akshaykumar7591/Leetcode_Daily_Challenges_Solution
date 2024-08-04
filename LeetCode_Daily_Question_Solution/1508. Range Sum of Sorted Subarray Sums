class Solution {

    public int rangeSum(int[] nums, int n, int left, int right) {
        ArrayList<Integer> storeSubarray = new ArrayList<>();
        for (int i = 0; i < nums.length; i++) {
            int sum = 0;
            // Iterate through all indices ahead of the current index.
            for (int j = i; j < nums.length; j++) {
                sum += nums[j];
                storeSubarray.add(sum);
            }
        }
        // Sort all subarray sum values in increasing order.
        Collections.sort(storeSubarray);

        // Find the sum of all values between left and right.
        int rangeSum = 0, mod = (int) 1e9 + 7;
        for (int i = left - 1; i <= right - 1; i++) {
            rangeSum = (rangeSum + storeSubarray.get(i)) % mod;
        }
        return rangeSum;
    }
}
