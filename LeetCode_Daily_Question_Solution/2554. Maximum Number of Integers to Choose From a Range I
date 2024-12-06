class Solution {

    public int maxCount(int[] banned, int n, int maxSum) {
        // Store banned numbers in HashSet
        Set<Integer> bannedSet = new HashSet<>();
        for (int num : banned) {
            bannedSet.add(num);
        }

        // Track count of valid numbers we can choose
        int count = 0;

        // Try each number from 1 to n
        for (int num = 1; num <= n; num++) {
            // Skip banned numbers
            if (bannedSet.contains(num)) continue;

            // Return if adding current number exceeds maxSum
            if (maxSum - num < 0) return count;

            // Include current number
            maxSum -= num;
            count++;
        }
        return count;
    }
}
