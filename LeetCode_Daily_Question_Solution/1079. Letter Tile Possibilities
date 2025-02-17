class Solution {

    public int numTilePossibilities(String tiles) {
        Set<String> seen = new HashSet<>();

        // Sort characters to handle duplicates efficiently
        char[] chars = tiles.toCharArray();
        Arrays.sort(chars);
        String sortedTiles = new String(chars);

        // Find all unique sequences and their permutations
        return generateSequences(sortedTiles, "", 0, seen) - 1;
    }

    private int factorial(int n) {
        if (n <= 1) {
            return 1;
        }

        int result = 1;
        for (int num = 2; num <= n; num++) {
            result *= num;
        }
        return result;
    }

    private int countPermutations(String seq) {
        // Count frequency of each character
        int[] charCount = new int[26];
        for (char ch : seq.toCharArray()) {
            charCount[ch - 'A']++;
        }

        // Calculate permutations using factorial formula
        int total = factorial(seq.length());
        for (int count : charCount) {
            total /= factorial(count);
        }
        return total;
    }

    private int generateSequences(
        String tiles,
        String current,
        int pos,
        Set<String> seen
    ) {
        if (pos >= tiles.length()) {
            // If new sequence found, count its unique permutations
            if (seen.add(current)) {
                return countPermutations(current);
            }
            return 0;
        }

        // Try including and excluding current character
        return (
            generateSequences(tiles, current, pos + 1, seen) +
            generateSequences(tiles, current + tiles.charAt(pos), pos + 1, seen)
        );
    }
}
