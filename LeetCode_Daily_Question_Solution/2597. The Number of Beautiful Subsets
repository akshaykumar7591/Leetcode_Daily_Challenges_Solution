class Solution {
    public int beautifulSubsets(int[] nums, int k) {
        return countBeautifulSubsets(nums, k, 0, 0);
    }

    private int countBeautifulSubsets(int[] nums, int difference, int index, int mask) {
        // Base case: Return 1 if mask is greater than 0 (non-empty subset)
        if (index == nums.length)
            return mask > 0 ? 1 : 0;

        // Flag to check if the current subset is beautiful
        boolean isBeautiful = true;

        // Check if the current number forms a beautiful pair with any previous number
        // in the subset
        for (int j = 0; j < index && isBeautiful; ++j){
            isBeautiful = ((1 << j) & mask) == 0 || 
                        Math.abs(nums[j] - nums[index]) != difference;
            }

        // Recursively calculate beautiful subsets including and excluding the current
        // number
        int skip = countBeautifulSubsets(nums, difference, index + 1, mask);
        int take;
        if (isBeautiful) {
            take = countBeautifulSubsets(nums, difference,
                    index + 1, mask + (1 << index));
        } else {
            take = 0;
        }

        return skip + take;
    }
}
