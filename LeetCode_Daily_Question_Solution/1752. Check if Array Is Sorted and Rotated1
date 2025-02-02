class Solution {

    public boolean check(int[] nums) {
        int n = nums.length;
        if (n <= 1) return true;

        int inversionCount = 0;

        // For every pair, count the number of inversions.
        for (int i = 1; i < n; ++i) {
            if (nums[i] < nums[i - 1]) {
                ++inversionCount;
            }
        }

        // Also check between the last and the first element due to rotation
        if (nums[0] < nums[n - 1]) {
            ++inversionCount;
        }

        return inversionCount <= 1;
    }
}
