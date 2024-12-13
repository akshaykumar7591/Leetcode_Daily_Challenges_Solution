class Solution {

    public long findScore(int[] nums) {
        long ans = 0;
        boolean[] marked = new boolean[nums.length];

        PriorityQueue<int[]> heap = new PriorityQueue<>((arr1, arr2) -> {
            if (arr1[0] != arr2[0]) return arr1[0] - arr2[0];
            return arr1[1] - arr2[1];
        });

        for (int i = 0; i < nums.length; i++) {
            heap.add(new int[] { nums[i], i });
        }

        while (!heap.isEmpty()) {
            int[] element = heap.remove();
            int number = element[0];
            int index = element[1];
            if (!marked[index]) {
                ans += number;
                marked[index] = true;
                // mark adjacent elements if they exist
                if (index - 1 >= 0) {
                    marked[index - 1] = true;
                }
                if (index + 1 < nums.length) {
                    marked[index + 1] = true;
                }
            }
        }

        return ans;
    }
}
