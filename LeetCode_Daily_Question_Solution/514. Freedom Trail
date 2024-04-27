class Solution {
    public int findRotateSteps(String ring, String key) {
        int ringLen = ring.length();
        int keyLen = key.length();
        int[][] bestSteps = new int[ringLen][keyLen + 1];
        // Initialize values of best_steps to largest integer
        for (int[] row : bestSteps) {
            Arrays.fill(row, Integer.MAX_VALUE);
        }
        // Initialize last column to zero to represent the word has been spelled 
        for (int i = 0; i < ring.length(); i++) {
            bestSteps[i][keyLen] = 0;
        }
        // For each occurrence of the character at keyIndex of key in ring
        // Stores minimum steps to the character from ringIndex of ring
        for (int keyIndex = keyLen - 1; keyIndex >= 0; keyIndex--) {
            for (int ringIndex = 0; ringIndex < ringLen; ringIndex++) {
                for (int charIndex = 0; charIndex < ringLen; charIndex++) {
                    if (ring.charAt(charIndex) == key.charAt(keyIndex)) {
                        bestSteps[ringIndex][keyIndex] = Math.min(bestSteps[ringIndex][keyIndex],
                                1 + countSteps(ringIndex, charIndex, ringLen)
                                + bestSteps[charIndex][keyIndex + 1]);
                    }
                }
            }
        }
        return bestSteps[0][0];
    }

    // Find the minimum steps between two indexes of ring
    private int countSteps(int curr, int next, int ringLength) {
        int stepsBetween = Math.abs(curr - next);
        int stepsAround = ringLength - stepsBetween;
        return Math.min(stepsBetween, stepsAround);
    }
}
