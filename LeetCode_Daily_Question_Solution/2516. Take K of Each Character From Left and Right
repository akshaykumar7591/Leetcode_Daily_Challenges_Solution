class Solution {

    int minMinutes = Integer.MAX_VALUE;

    public int takeCharacters(String s, int k) {
        if (k == 0) return 0;
        int[] count = new int[3];
        solve(s, k, 0, s.length() - 1, count, 0);
        return minMinutes == Integer.MAX_VALUE ? -1 : minMinutes;
    }

    private void solve(
        String s,
        int k,
        int left,
        int right,
        int[] count,
        int minutes
    ) {
        // Base case: check if we have k of each character
        if (count[0] >= k && count[1] >= k && count[2] >= k) {
            minMinutes = Math.min(minMinutes, minutes);
            return;
        }

        // If we can't take more characters
        if (left > right) return;

        // Take from left
        int[] leftCount = count.clone();
        leftCount[s.charAt(left) - 'a']++;
        solve(s, k, left + 1, right, leftCount, minutes + 1);

        // Take from right
        int[] rightCount = count.clone();
        rightCount[s.charAt(right) - 'a']++;
        solve(s, k, left, right - 1, rightCount, minutes + 1);
    }
}
