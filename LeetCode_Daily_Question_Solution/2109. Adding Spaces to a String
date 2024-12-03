class Solution {

    public String addSpaces(String s, int[] spaces) {
        // StringBuilder for efficient string construction
        StringBuilder result = new StringBuilder();
        int spaceIndex = 0;

        for (int stringIndex = 0; stringIndex < s.length(); stringIndex++) {
            if (
                spaceIndex < spaces.length && stringIndex == spaces[spaceIndex]
            ) {
                // Insert space at the correct position
                result.append(' ');
                spaceIndex++;
            }
            // Append the current character
            result.append(s.charAt(stringIndex));
        }
        return result.toString();
    }
}
