public class Solution {

    public int[] missingRolls(int[] rolls, int mean, int n) {
        int sum = 0;
        for (int roll : rolls) {
            sum = sum + roll;
        }
        // Find the remaining sum.
        int remainingSum = mean * (n + rolls.length) - sum;
        // Check if sum is valid or not.
        if (remainingSum > 6 * n || remainingSum < n) {
            return new int[0];
        }
        int distributeMean = remainingSum / n;
        int mod = remainingSum % n;
        // Distribute the remaining mod elements in nElements array.
        int[] nElements = new int[n];
        Arrays.fill(nElements, distributeMean);
        for (int i = 0; i < mod; i++) {
            nElements[i]++;
        }
        return nElements;
    }
}
