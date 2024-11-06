class Solution {

    public boolean canSortArray(int[] nums) {
        // Avoid modifying the input directly
        int[] values = Arrays.copyOf(nums, nums.length);

        int n = values.length;

        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n - i - 1; j++) {
                if (values[j] <= values[j + 1]) {
                    // No swap needed
                    continue;
                } else {
                    if (
                        Integer.bitCount(values[j]) ==
                        Integer.bitCount(values[j + 1])
                    ) {
                        // Swap the elements
                        int temp = values[j];
                        values[j] = values[j + 1];
                        values[j + 1] = temp;
                    } else {
                        return false;
                    }
                }
            }
        }
        return true;
    }
}
