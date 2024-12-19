class Solution {

    public int maxChunksToSorted(int[] arr) {
        int n = arr.length;
        int chunks = 0, maxElement = 0;

        // Iterate over the array
        for (int i = 0; i < n; i++) {
            // Update maxElement
            maxElement = Math.max(maxElement, arr[i]);

            if (maxElement == i) {
                // All values in range [0, i] belong to the prefix arr[0:i]; a new chunk can be formed
                chunks++;
            }
        }

        return chunks;
    }
}
