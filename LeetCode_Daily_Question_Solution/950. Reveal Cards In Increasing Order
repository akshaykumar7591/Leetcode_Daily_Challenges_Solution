class Solution {
    public int[] deckRevealedIncreasing(int[] deck) {
        int N = deck.length;
        int[] result = new int[N];
        boolean skip = false;
        int indexInDeck = 0;
        int indexInResult = 0;

        Arrays.sort(deck);

        while (indexInDeck < N) {
            // There is an available gap in result
            if (result[indexInResult] == 0) {

                // Add a card to result
                if (!skip) {
                    result[indexInResult] = deck[indexInDeck];
                    indexInDeck++;
                }

                // Toggle skip to alternate between adding and skipping cards
                skip = !skip;
            }
            // Progress to next index of result array
            indexInResult = (indexInResult + 1) % N;
        }
        return result;
    }
}
