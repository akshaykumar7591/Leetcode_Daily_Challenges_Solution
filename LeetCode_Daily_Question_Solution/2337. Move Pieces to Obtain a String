public class Solution {

    public boolean canChange(String start, String target) {
        int startLength = start.length();
        // Pointers for start string and target string
        int startIndex = 0, targetIndex = 0;

        while (startIndex < startLength || targetIndex < startLength) {
            // Skip underscores in start
            while (
                startIndex < startLength && start.charAt(startIndex) == '_'
            ) {
                startIndex++;
            }
            // Skip underscores in target
            while (
                targetIndex < startLength && target.charAt(targetIndex) == '_'
            ) {
                targetIndex++;
            }
            // If one string is exhausted, both should be exhausted
            if (startIndex == startLength || targetIndex == startLength) {
                return startIndex == startLength && targetIndex == startLength;
            }

            // Check if the pieces match and follow movement rules
            if (
                start.charAt(startIndex) != target.charAt(targetIndex) ||
                (start.charAt(startIndex) == 'L' && startIndex < targetIndex) ||
                (start.charAt(startIndex) == 'R' && startIndex > targetIndex)
            ) return false;

            startIndex++;
            targetIndex++;
        }

        // If all conditions are satisfied, return true
        return true;
    }
}
