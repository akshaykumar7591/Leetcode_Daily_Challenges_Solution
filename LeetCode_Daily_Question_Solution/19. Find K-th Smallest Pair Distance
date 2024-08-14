class Solution {

    public int smallestDistancePair(int[] nums, int k) {
        int arrayLength = nums.length;

        // Find the maximum element in the array
        int maxElement = Integer.MIN_VALUE;
        for (int num : nums) {
            maxElement = Math.max(maxElement, num);
        }

        // Initialize a bucket array to store counts of each distance
        int[] distanceBucket = new int[maxElement + 1];

        // Populate the bucket array with counts of each distance
        for (int i = 0; i < arrayLength; ++i) {
            for (int j = i + 1; j < arrayLength; ++j) {
                // Compute the distance between nums[i] and nums[j]
                int distance = Math.abs(nums[i] - nums[j]);

                // Increment the count for this distance in the bucket
                ++distanceBucket[distance];
            }
        }

        // Find the k-th smallest distance
        for (int dist = 0; dist <= maxElement; ++dist) {
            // Reduce k by the number of pairs with the current distance
            k -= distanceBucket[dist];

            // If k is less than or equal to 0, return the current distance
            if (k <= 0) {
                return dist;
            }
        }

        return -1; // Return -1 if no distance found, should not reach here
    }
}
