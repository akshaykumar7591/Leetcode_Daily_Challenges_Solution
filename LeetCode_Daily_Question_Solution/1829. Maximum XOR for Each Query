class Solution {

    public int[] getMaximumXor(int[] nums, int maximumBit) {
        int[] prefixXOR = new int[nums.length];
        prefixXOR[0] = nums[0];
        for (int i = 1; i < nums.length; i++) {
            prefixXOR[i] = prefixXOR[i - 1] ^ nums[i];
        }
        int[] ans = new int[nums.length];

        int mask = (1 << maximumBit) - 1;

        for (int i = 0; i < nums.length; i++) {
            // find k to maximize value
            int currentXOR = prefixXOR[prefixXOR.length - 1 - i];
            ans[i] = currentXOR ^ mask;
        }

        return ans;
    }
}
