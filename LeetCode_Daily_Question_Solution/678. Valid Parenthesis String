class Solution {
    public boolean checkValidString(String s) {
        int n = s.length();
        int[][] memo = new int[n][n];
        for (int[] row: memo) {
            Arrays.fill(row, -1);
        }
        return isValidString(0, 0, s, memo);
    }

    private boolean isValidString(int index, int openCount, String str, int[][] memo) {
        // If reached end of the string, check if all brackets are balanced
        if (index == str.length()) {
            return (openCount == 0);
        }
        // If already computed, return memoized result
        if (memo[index][openCount] != -1) {
            return memo[index][openCount] == 1;
        }
        boolean isValid = false;
        // If encountering '*', try all possibilities
        if (str.charAt(index) == '*') {
            isValid |= isValidString(index + 1, openCount + 1, str, memo); // Treat '*' as '('
            if (openCount > 0) {
                isValid |= isValidString(index + 1, openCount - 1, str, memo); // Treat '*' as ')'
            }
            isValid |= isValidString(index + 1, openCount, str, memo); // Treat '*' as empty
        } else {
            // Handle '(' and ')'
            if (str.charAt(index) == '(') {
                isValid = isValidString(index + 1, openCount + 1, str, memo); // Increment count for '('
            } else if (openCount > 0) {
                isValid = isValidString(index + 1, openCount - 1, str, memo); // Decrement count for ')'
            }
        }

        // Memoize and return the result
        memo[index][openCount] = isValid ? 1 : 0;
        return isValid;
    }
}
