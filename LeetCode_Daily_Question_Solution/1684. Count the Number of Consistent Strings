class Solution {

    public int countConsistentStrings(String allowed, String[] words) {
        int consistentCount = 0;

        // Iterate through each word in the words array
        for (String word : words) {
            boolean isWordConsistent = true;

            // Check each character in the current word
            for (int i = 0; i < word.length(); i++) {
                char currentChar = word.charAt(i);
                boolean isCharAllowed = false;

                // Check if the current character is in the allowed string
                for (int j = 0; j < allowed.length(); j++) {
                    if (allowed.charAt(j) == currentChar) {
                        isCharAllowed = true;
                        break; // Character found, no need to continue searching
                    }
                }

                // If the character is not allowed, mark the word as inconsistent
                if (!isCharAllowed) {
                    isWordConsistent = false;
                    break; // No need to check remaining characters
                }
            }

            // If the word is consistent, increment the count
            if (isWordConsistent) {
                consistentCount++;
            }
        }

        return consistentCount;
    }
}
