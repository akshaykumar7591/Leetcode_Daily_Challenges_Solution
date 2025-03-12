class Solution {

    // Return the first index where the value is equal to or greater than zero.
    private int lowerBound(int[] nums) {
        int start = 0, end = nums.length - 1;
        int index = nums.length;

        while (start <= end) {
            int mid = (start + end) / 2;

            if (nums[mid] < 0) {
                start = mid + 1;
            } else if (nums[mid] >= 0) {
                end = mid - 1;
                index = mid;
            }
        }

        return index;
    }

    // Return the first index where the value is greater than zero.
    private int upperBound(int[] nums) {
        int start = 0, end = nums.length - 1;
        int index = nums.length;

        while (start <= end) {
            int mid = (start + end) / 2;

            if (nums[mid] <= 0) {
                start = mid + 1;
            } else if (nums[mid] > 0) {
                end = mid - 1;
                index = mid;
            }
        }

        return index;
    }

    public int maximumCount(int[] nums) {
        // All integers from the first non-zero to last will be positive
        // integers.
        int positiveCount = nums.length - upperBound(nums);
        // All integers from the index 0 to index before the first zero index
        // will be negative.
        int negativeCount = lowerBound(nums);

        return Math.max(positiveCount, negativeCount);
    }
}
