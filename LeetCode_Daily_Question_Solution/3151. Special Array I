class Solution {

    public boolean isArraySpecial(int[] nums) {
        // Iterate through indexes 0 to n - 1
        for (int index = 0; index < nums.length - 1; index++) {
            // Compare the parities using bitwise operations
            if (((nums[index] & 1) ^ (nums[index + 1] & 1)) == 0) {
                // If the two adjacent numbers have the same parity, return false
                return false;
            }
        }

        // Return true if no pair of adjacent numbers with the same parity are found
        return true;
    }
}
