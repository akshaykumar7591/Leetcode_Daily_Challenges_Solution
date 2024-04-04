class Solution {
    public int maxDepth(String s) {
        int ans = 0;
        int openBrackets = 0;

        for (Character c : s.toCharArray()) {
            if (c == '(') {
                openBrackets++;
            } else if (c == ')') {
                openBrackets--;
            }

            ans = Math.max(ans, openBrackets);
        }

        return ans;
    }
}
