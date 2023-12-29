class Solution {
    public int minDifficulty(int[] jobDifficulty, int d) {
        if (jobDifficulty.length < d) {
            return -1;
        }
        int len = jobDifficulty.length;
        int sum = 0;
        for (int i = 0; i < jobDifficulty.length; i++) {
            sum += jobDifficulty[i];
        }
        if (sum == 0) {
            return 0;
        }
        int[][] memo = new int[d + 1][len];
        helper(jobDifficulty, d, 0, memo);
        
        return memo[d][0];
    }

    private void helper(int[] jd, int daysLeft, int idx, int[][] memo) {
        int len = jd.length;
        if (memo[daysLeft][idx] != 0) {
            return;
        }
        if (daysLeft == 1) {
            int num = 0;
            for (int i = idx; i < len; i++) {
                num = Math.max(num, jd[i]);
            }
            memo[daysLeft][idx] = num;
            return;
        }
        int max = jd[idx];
        daysLeft--;
        int stop = len - idx - daysLeft + 1;
    
        int res = Integer.MAX_VALUE;
        for (int i = 1; i < stop; i++) {
            max = Math.max(max, jd[idx + i - 1]);
            int other = memo[daysLeft][idx + i];
            if (other == 0) {
                helper(jd, daysLeft, idx + i, memo);
                other = memo[daysLeft][idx + i];
            }
            res = Math.min(res, other + max);   
        }
        memo[daysLeft + 1][idx] = res;
    }

}
