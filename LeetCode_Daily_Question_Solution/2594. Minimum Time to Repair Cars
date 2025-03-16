class Solution {

    public long repairCars(int[] ranks, int cars) {
        // Count the frequency of each rank
        Map<Integer, Integer> count = new HashMap<>();
        for (int rank : ranks) {
            count.put(rank, count.getOrDefault(rank, 0) + 1);
        }

        // Create a Min-heap storing [time, rank, n, count]
        // - time: time for the next repair
        // - rank: mechanic's rank
        // - n: cars repaired by this mechanic
        // - count: number of mechanics with this rank
        // Initial time = rank (as rank * 1^2 = rank)
        PriorityQueue<long[]> minHeap = new PriorityQueue<>((a, b) ->
            Long.compare(a[0], b[0])
        );

        // Add initial entries to the heap
        for (int rank : count.keySet()) {
            // Elements: [time, rank, cars_repaired, mechanic_count]
            minHeap.offer(new long[] { rank, rank, 1, count.get(rank) });
        }

        long time = 0;
        // Process until all cars are repaired
        while (cars > 0) {
            // Pop the mechanic with the smallest current repair time
            long[] current = minHeap.poll();
            time = current[0];
            int rank = (int) current[1];
            long n = current[2];
            int mechCount = (int) current[3];

            // Deduct the number of cars repaired by this mechanic group
            cars -= mechCount;

            // Increment the number of cars repaired by this mechanic
            n += 1;

            // Push the updated repair time back into the heap
            // The new repair time is rank * n^2 (time increases quadratically with n)
            minHeap.offer(new long[] { rank * n * n, rank, n, mechCount });
        }

        return time;
    }
}
