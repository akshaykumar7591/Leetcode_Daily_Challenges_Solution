public class Solution {

    public long pickGifts(int[] gifts, int k) {
        // Convert int[] to List<Integer> manually for efficient initialization of the heap
        // Negate values to simulate max-heap
        List<Integer> giftsList = new ArrayList<>();
        for (int gift : gifts) {
            giftsList.add(-gift);
        }

        // Initialize giftsHeap from giftsList
        PriorityQueue<Integer> giftsHeap = new PriorityQueue<>(giftsList);
        // Perform the operation 'k' times
        for (int i = 0; i < k; i++) {
            // Get the maximum element from the heap (top element)
            int maxElement = -giftsHeap.poll();

            // Insert the floor of the square root of the maximum element back into the heap
            giftsHeap.offer(-(int) Math.sqrt(maxElement));
        }

        // Accumulate the sum of the elements in the heap
        long numberOfRemainingGifts = 0;
        while (!giftsHeap.isEmpty()) {
            numberOfRemainingGifts -= giftsHeap.poll();
        }

        return numberOfRemainingGifts;
    }
}
