class Solution {

    public boolean canConstruct(String s, int k) {
        // Handle edge cases
        if (s.length() < k) return false;
        if (s.length() == k) return true;

        // Initialize oddCount as an integer bitmask
        int oddCount = 0;

        // Update the bitmask for each character in the string
        for (char chr : s.toCharArray()) {
            oddCount ^= 1 << (chr - 'a');
        }

        // Return if the number of odd frequencies is less than or equal to k
        return Integer.bitCount(oddCount) <= k;
    }
}
