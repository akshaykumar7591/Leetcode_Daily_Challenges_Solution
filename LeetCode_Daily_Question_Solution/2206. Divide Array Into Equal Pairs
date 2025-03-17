class Solution {

    public boolean divideArray(int[] nums) {
        // Track unpaired numbers
        Set<Integer> unpaired = new HashSet<>();

        // Add numbers to set if unseen, remove if seen
        for (int num : nums) {
            if (unpaired.contains(num)) {
                unpaired.remove(num);
            } else {
                unpaired.add(num);
            }
        }

        // Return true if all numbers were paired
        return unpaired.isEmpty();
    }
}
