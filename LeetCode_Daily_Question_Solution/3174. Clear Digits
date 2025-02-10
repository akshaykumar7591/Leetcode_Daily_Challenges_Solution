public class Solution {

    public String clearDigits(String s) {
        // This variable keeps track of the actual length of the resulting string
        int answerLength = 0;
        char[] charArray = s.toCharArray();

        // Iterate through each character in the input string
        for (int charIndex = 0; charIndex < s.length(); charIndex++) {
            // If the current character is a digit
            if (Character.isDigit(s.charAt(charIndex))) {
                // Decrement answerLength to remove the last character from the result
                answerLength = Math.max(answerLength - 1, 0);
            } else {
                // Place the character in the "answer" portion of the string
                charArray[answerLength++] = s.charAt(charIndex);
            }
        }

        // Resize the string to match the actual length of the answer
        s = new String(charArray, 0, answerLength);

        return s;
    }
}
