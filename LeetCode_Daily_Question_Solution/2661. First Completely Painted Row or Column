class Solution {

    public int firstCompleteIndex(int[] arr, int[][] mat) {
        // Map to store the index of each number in the arr
        Map<Integer, Integer> numToIndex = new HashMap<Integer, Integer>();
        for (int i = 0; i < arr.length; i++) {
            numToIndex.put(arr[i], i);
        }

        int result = Integer.MAX_VALUE;
        int numRows = mat.length;
        int numCols = mat[0].length;

        // Check for the earliest row to be completely painted
        for (int row = 0; row < numRows; row++) {
            // Tracks the greatest index in this row
            int lastElementIndex = Integer.MIN_VALUE;
            for (int col = 0; col < numCols; col++) {
                int indexVal = numToIndex.get(mat[row][col]);
                lastElementIndex = Math.max(lastElementIndex, indexVal);
            }
            // Update result with the minimum index where this row is fully painted
            result = Math.min(result, lastElementIndex);
        }

        // Check for the earliest column to be completely painted
        for (int col = 0; col < numCols; col++) {
            int lastElementIndex = Integer.MIN_VALUE;
            for (int row = 0; row < numRows; row++) {
                int indexVal = numToIndex.get(mat[row][col]);
                lastElementIndex = Math.max(lastElementIndex, indexVal);
            }
            // Update result with the minimum index where this column is fully painted
            result = Math.min(result, lastElementIndex);
        }

        return result;
    }
}
