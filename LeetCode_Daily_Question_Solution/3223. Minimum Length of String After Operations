class Solution {

    public int minimumLength(String s) {
        // Step 1: Initialize a frequency array to count occurrences of each character
        int[] charFrequency = new int[26];
        int totalLength = 0;

        // Step 2: Count the frequency of each character in the string
        for (char currentChar : s.toCharArray()) {
            charFrequency[currentChar - 'a']++;
        }

        // Step 3: Calculate the total length after deletions count
        for (int frequency : charFrequency) {
            if (frequency == 0) continue; // Skip characters that don't appear
            if (frequency % 2 == 0) {
                totalLength += 2; // If frequency is even, add 2 characters
            } else {
                totalLength += 1; // If frequency is odd, add 1 character
            }
        }

        // Step 4: Return the minimum length after deletions count
        return totalLength;
    }
}
