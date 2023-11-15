class Solution {
    public int maximumElementAfterDecrementingAndRearranging(int[] arr) {
        Arrays.sort(arr);
        arr[0] = 1; // first condition

        for (int i = 1; i < arr.length; ++i) {
            if (Math.abs(arr[i] - arr[i - 1]) <= 1) {
                continue; // purposely wrote for understanding
            } else {
                arr[i] = arr[i - 1] + 1; // second condition
            }
        }

        return arr[arr.length - 1]; 
    }
}
