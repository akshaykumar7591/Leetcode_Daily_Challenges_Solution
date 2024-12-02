class Solution {

    public int isPrefixOfWord(String sentence, String searchWord) {
        // Check for invalid input
        if (
            sentence == null ||
            searchWord == null ||
            searchWord.length() > sentence.length()
        ) {
            return -1;
        }

        // Initialize the word position counter
        int currentWordPosition = 1;
        // Initialize the current index in the sentence
        int currentIndex = 0;
        // Get the length of the sentence
        int sentenceLength = sentence.length();

        // Loop through the sentence
        while (currentIndex < sentenceLength) {
            // Skip leading spaces
            while (
                currentIndex < sentenceLength &&
                sentence.charAt(currentIndex) == ' '
            ) {
                currentWordPosition++;
                while (
                    currentIndex < sentenceLength &&
                    sentence.charAt(currentIndex) == ' '
                ) {
                    currentIndex++;
                }
            }

            // Check if the current word starts with searchWord
            int matchCount = 0;
            while (
                currentIndex < sentenceLength &&
                matchCount < searchWord.length() &&
                sentence.charAt(currentIndex) == searchWord.charAt(matchCount)
            ) {
                currentIndex++;
                matchCount++;
            }

            // If the entire searchWord matches, return the current word position
            if (matchCount == searchWord.length()) {
                return currentWordPosition;
            }

            // Move to the end of the current word
            while (
                currentIndex < sentenceLength &&
                sentence.charAt(currentIndex) != ' '
            ) {
                currentIndex++;
            }
        }

        // If no match is found, return -1
        return -1;
    }
}
