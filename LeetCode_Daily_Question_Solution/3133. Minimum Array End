class Solution {

    public long minEnd(int n, int x) {
        long result = x;

        // Step 1: Iterate n-1 times (since we already initialized result with x)
        while (--n > 0) {
            // Step 2: Increment result and perform bitwise OR with x
            result = (result + 1) | x;
        }

        return result;
    }
}
