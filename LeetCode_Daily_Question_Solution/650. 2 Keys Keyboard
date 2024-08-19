class Solution {

    int n;

    public int minSteps(int n) {
        if (n == 1) return 0;
        this.n = n;
        // first step is always a Copy All operation
        return 1 + minStepsHelper(1, 1);
    }

    private int minStepsHelper(int currLen, int pasteLen) {
        // base case: reached n A's, don't need more operations
        if (currLen == n) return 0;
        // base case: exceeded n `A`s, not a valid sequence, so
        // return max value
        if (currLen > n) return 1000;

        // copy all + paste
        int opt1 = 2 + minStepsHelper(currLen * 2, currLen);
        // paste
        int opt2 = 1 + minStepsHelper(currLen + pasteLen, pasteLen);

        return Math.min(opt1, opt2);
    }
}
