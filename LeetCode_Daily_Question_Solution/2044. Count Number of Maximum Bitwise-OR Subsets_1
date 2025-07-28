class Solution {

    public int countMaxOrSubsets(int[] nums) {
        int n = nums.length;
        int maxOrValue = 0;

        // Calculate the maximum OR value
        for (int num : nums) {
            maxOrValue |= num;
        }

        Integer[][] memo = new Integer[n][maxOrValue + 1];

        return countSubsetsRecursive(nums, 0, 0, maxOrValue, memo);
    }

    private int countSubsetsRecursive(
        int[] nums,
        int index,
        int currentOr,
        int targetOr,
        Integer[][] memo
    ) {
        // Base case: reached the end of the array
        if (index == nums.length) {
            return (currentOr == targetOr) ? 1 : 0;
        }

        // Check if the result for this state is already memoized
        if (memo[index][currentOr] != null) {
            return memo[index][currentOr];
        }

        // Don't include the current number
        int countWithout = countSubsetsRecursive(
            nums,
            index + 1,
            currentOr,
            targetOr,
            memo
        );

        // Include the current number
        int countWith = countSubsetsRecursive(
            nums,
            index + 1,
            currentOr | nums[index],
            targetOr,
            memo
        );

        // Memoize and return the result
        return memo[index][currentOr] = countWithout + countWith;
    }
}
