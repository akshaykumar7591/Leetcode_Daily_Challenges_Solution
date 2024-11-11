public class Solution {

    public boolean checkPrime(int x) {
        for (int i = 2; i <= Math.sqrt(x); i++) {
            if (x % i == 0) {
                return false;
            }
        }
        return true;
    }

    public boolean primeSubOperation(int[] nums) {
        for (int i = 0; i < nums.length; i++) {
            int bound;
            // In case of first index, we need to find the largest prime less than nums[0].
            if (i == 0) {
                bound = nums[0];
            } else {
                // Otherwise, we need to find the largest prime, that makes the current element closest to the previous element.
                bound = nums[i] - nums[i - 1];
            }

            // If the bound is less than or equal to 0, then the array cannot be made strictly increasing.
            if (bound <= 0) {
                return false;
            }

            // Find the largest prime less than bound.
            int largestPrime = 0;
            for (int j = bound - 1; j >= 2; j--) {
                if (checkPrime(j)) {
                    largestPrime = j;
                    break;
                }
            }

            // Subtract this value from nums[i].
            nums[i] = nums[i] - largestPrime;
        }
        return true;
    }
}
