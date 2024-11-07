class Solution {

    public int largestCombination(int[] candidates) {
        // Initialize an array to store the count of each bit position.
        int[] bitCount = new int[24];
        for (int i = 0; i < 24; i++) {
            for (int num : candidates) {
                // Check if the i-th bit is set.
                if ((num & (1 << i)) != 0) {
                    bitCount[i]++;
                }
            }
        }
        // Return the maximum count.
        int max = 0;
        for (int count : bitCount) {
            if (count > max) {
                max = count;
            }
        }
        return max;
    }
}
