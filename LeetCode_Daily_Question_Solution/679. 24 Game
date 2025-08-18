class Solution {
    public boolean judgePoint24(int[] cards) {
        List<Double> nums = new ArrayList<>();
        for (int card : cards) nums.add((double) card);
        return solve(nums);
    }

    private boolean solve(List<Double> nums) {
        if (nums.size() == 1) {
            return Math.abs(nums.get(0) - 24.0) < 1e-6;
        }

        int n = nums.size();
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                if (i == j) continue;

                List<Double> next = new ArrayList<>();
                for (int k = 0; k < n; k++) {
                    if (k != i && k != j) next.add(nums.get(k));
                }

                double a = nums.get(i), b = nums.get(j);
                List<Double> results = new ArrayList<>();
                results.add(a + b);
                results.add(a - b);
                results.add(b - a);
                results.add(a * b);
                if (Math.abs(b) > 1e-6) results.add(a / b);
                if (Math.abs(a) > 1e-6) results.add(b / a);

                for (double val : results) {
                    next.add(val);
                    if (solve(next)) return true;
                    next.remove(next.size() - 1);
                }
            }
        }
        return false;
    }
}
