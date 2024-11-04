class Solution {

    public String compressedString(String word) {
        StringBuilder comp = new StringBuilder("");

        // pos tracks our position in the input string
        int pos = 0;

        // Process until we reach end of string
        while (pos < word.length()) {
            int consecutiveCount = 0;

            char currentChar = word.charAt(pos);

            // Count consecutive occurrences (maximum 9)
            while (
                pos < word.length() &&
                consecutiveCount < 9 &&
                word.charAt(pos) == currentChar
            ) {
                consecutiveCount++;
                pos++;
            }

            // Append count followed by character to result
            comp.append(consecutiveCount).append(currentChar);
        }

        return comp.toString();
    }
}
