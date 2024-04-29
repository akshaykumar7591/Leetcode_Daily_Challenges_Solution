class Solution {
    public int minOperations(int[] nums, int k) {
        int finalXor = 0;
        for (int n : nums) {
            finalXor = finalXor ^ n;
        }
        
        return Integer.bitCount(finalXor ^ k);
    }
}
