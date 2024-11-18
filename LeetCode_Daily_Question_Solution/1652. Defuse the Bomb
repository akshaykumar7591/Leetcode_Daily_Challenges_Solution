class Solution {

    public int[] decrypt(int[] code, int k) {
        int[] result = new int[code.length];
        // If k is 0, return the result directly.
        if (k == 0) {
            return result;
        }
        for (int i = 0; i < result.length; i++) {
            if (k > 0) {
                // If k is greater than 0, store the sum of next k numbers.
                for (int j = i + 1; j < i + k + 1; j++) {
                    result[i] += code[j % code.length];
                }
            } else {
                // If k is less than 0, store the sum of previous -1*k numbers.
                for (int j = i - Math.abs(k); j < i; j++) {
                    result[i] += code[(j + code.length) % code.length];
                }
            }
        }
        return result;
    }
}
