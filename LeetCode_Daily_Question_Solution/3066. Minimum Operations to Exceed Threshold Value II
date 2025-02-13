class Solution {

    public int minOperations(int[] nums, int k) {
        PriorityQueue<Long> minHeap = new PriorityQueue<Long>(
            Arrays.stream(nums)
                .mapToLong(i -> (long) i)
                .boxed()
                .collect(Collectors.toList())
        );
        int numOperations = 0;

        while (minHeap.peek() < k) {
            long x = minHeap.remove();
            long y = minHeap.remove();
            minHeap.add(Math.min(x, y) * 2 + Math.max(x, y));

            numOperations++;
        }
        return numOperations;
    }
}
