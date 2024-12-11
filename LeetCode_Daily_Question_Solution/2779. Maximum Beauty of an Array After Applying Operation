class Solution {

    public int maximumBeauty(int[] nums, int k) {
        // If there's only one element, the maximum beauty is 1
        if (nums.length == 1) return 1;

        int maxBeauty = 0;
        int maxValue = 0;

        // Find the maximum value in the array
        for (int num : nums) maxValue = Math.max(maxValue, num);

        // Create an array to keep track of the count changes
        int[] count = new int[maxValue + 1];

        // Update the count array for each value's range [val - k, val + k]
        for (int num : nums) {
            count[Math.max(num - k, 0)]++; // Increment at the start of the range
            count[Math.min(num + k + 1, maxValue)]--; // Decrement after the range
        }

        int currentSum = 0; // Tracks the running sum of counts
        // Calculate the prefix sum and find the maximum value
        for (int val : count) {
            currentSum += val;
            maxBeauty = Math.max(maxBeauty, currentSum);
        }

        return maxBeauty;
    }
}
