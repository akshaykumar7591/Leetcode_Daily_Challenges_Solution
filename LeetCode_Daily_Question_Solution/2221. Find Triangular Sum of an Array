class Solution {

    public int triangularSum(int[] nums) {
        List<Integer> current = Arrays.stream(nums)
            .boxed()
            .collect(Collectors.toList());
        while (current.size() > 1) {
            List<Integer> newNums = new ArrayList<>();
            for (int i = 0; i < current.size() - 1; ++i) {
                newNums.add((current.get(i) + current.get(i + 1)) % 10);
            }
            current = newNums;
        }
        return current.get(0);
    }
}
