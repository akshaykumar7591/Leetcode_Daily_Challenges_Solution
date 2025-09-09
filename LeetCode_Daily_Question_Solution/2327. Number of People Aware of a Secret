class Solution {

    private static final int MOD = 1000000007;

    public int peopleAwareOfSecret(int n, int delay, int forget) {
        Deque<int[]> know = new LinkedList<>();
        Deque<int[]> share = new LinkedList<>();
        know.add(new int[] { 1, 1 });
        int knowCnt = 1;
        int shareCnt = 0;

        for (int i = 2; i <= n; i++) {
            if (!know.isEmpty() && know.peekFirst()[0] == i - delay) {
                int[] first = know.pollFirst();
                knowCnt = (knowCnt - first[1] + MOD) % MOD;
                shareCnt = (shareCnt + first[1]) % MOD;
                share.add(first);
            }
            if (!share.isEmpty() && share.peekFirst()[0] == i - forget) {
                int[] first = share.pollFirst();
                shareCnt = (shareCnt - first[1] + MOD) % MOD;
            }
            if (!share.isEmpty()) {
                knowCnt = (knowCnt + shareCnt) % MOD;
                know.add(new int[] { i, shareCnt });
            }
        }
        return (knowCnt + shareCnt) % MOD;
    }
}
