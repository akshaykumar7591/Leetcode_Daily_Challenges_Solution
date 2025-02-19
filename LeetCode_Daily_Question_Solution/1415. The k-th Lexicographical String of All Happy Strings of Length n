public class Solution {

    public String getHappyString(int n, int k) {
        // Calculate the total number of happy strings of length n
        int total = 3 * (1 << (n - 1));

        // If k is greater than the total number of happy strings, return an empty string
        if (k > total) return "";

        StringBuilder result = new StringBuilder(n);
        // Initialize result with 'a' characters
        for (int i = 0; i < n; i++) {
            result.append('a');
        }

        // Define mappings for the next smallest and greatest valid characters
        Map<Character, Character> nextSmallest = new HashMap<>();
        nextSmallest.put('a', 'b');
        nextSmallest.put('b', 'a');
        nextSmallest.put('c', 'a');

        Map<Character, Character> nextGreatest = new HashMap<>();
        nextGreatest.put('a', 'c');
        nextGreatest.put('b', 'c');
        nextGreatest.put('c', 'b');

        // Calculate the starting indices for strings beginning with 'a', 'b', and 'c'
        int startA = 1;
        int startB = startA + (1 << (n - 1));
        int startC = startB + (1 << (n - 1));

        // Determine the first character based on the value of k
        if (k < startB) {
            result.setCharAt(0, 'a');
            k -= startA;
        } else if (k < startC) {
            result.setCharAt(0, 'b');
            k -= startB;
        } else {
            result.setCharAt(0, 'c');
            k -= startC;
        }

        // Iterate through the remaining positions in the result string
        for (int charIndex = 1; charIndex < n; charIndex++) {
            // Calculate the midpoint of the group for the current character position
            int midpoint = (1 << (n - charIndex - 1));

            // Determine the next character based on the value of k
            if (k < midpoint) {
                result.setCharAt(
                    charIndex,
                    nextSmallest.get(result.charAt(charIndex - 1))
                );
            } else {
                result.setCharAt(
                    charIndex,
                    nextGreatest.get(result.charAt(charIndex - 1))
                );
                k -= midpoint;
            }
        }

        return result.toString();
    }
}
