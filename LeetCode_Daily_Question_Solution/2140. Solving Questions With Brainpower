class Solution {
    public long mostPoints(int[][] questions) {
        long[] dp = new long[questions.length];
        for (int i = questions.length - 1; i >= 0; i--) {
            int index = i + questions[i][1] + 1;
            if (index < questions.length) {
                dp[i] = dp[index] + questions[i][0];
            } else {
                dp[i] = questions[i][0];
            }
            if (i < questions.length - 1) {
                dp[i] = Math.max(dp[i + 1], dp[i]);
            }
        }
        return dp[0];
    }
}
