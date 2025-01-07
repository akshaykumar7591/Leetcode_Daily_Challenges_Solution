class Solution {

    class TrieNode {

        // Tracks how many times this substring appears in the Trie.
        int frequency;
        // Maps characters to their respective child nodes.
        Map<Character, TrieNode> childNodes;

        TrieNode() {
            frequency = 0;
            childNodes = new HashMap<>();
        }
    }

    public List<String> stringMatching(String[] words) {
        List<String> matchingWords = new ArrayList<>();
        TrieNode root = new TrieNode(); // Initialize the root of the Trie.

        // Insert all suffixes of each word into the Trie.
        for (String word : words) {
            for (int startIndex = 0; startIndex < word.length(); startIndex++) {
                // Insert each suffix starting from index startIndex.
                insertWord(root, word.substring(startIndex));
            }
        }

        // Check each word to see if it exists as a substring in the Trie.
        for (String word : words) {
            if (isSubstring(root, word)) {
                matchingWords.add(word);
            }
        }

        return matchingWords;
    }

    private void insertWord(TrieNode root, String word) {
        TrieNode currentNode = root;
        for (char c : word.toCharArray()) {
            // If the character already exists as a child node, move to it.
            currentNode.childNodes.putIfAbsent(c, new TrieNode());
            currentNode = currentNode.childNodes.get(c);
            currentNode.frequency++; // Increment the frequency of the node.
        }
    }

    private boolean isSubstring(TrieNode root, String word) {
        TrieNode currentNode = root;
        for (char c : word.toCharArray()) {
            // Traverse the Trie following the characters of the word.
            currentNode = currentNode.childNodes.get(c);
        }
        // A word is a substring if its frequency in the Trie is greater than 1.
        return currentNode.frequency > 1;
    }
}
