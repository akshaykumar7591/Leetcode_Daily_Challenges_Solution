class Node {

    private Node[] links = new Node[26];

    // Check if the character is present in the current node
    public boolean contains(char c) {
        return links[c - 'a'] != null;
    }

    // Insert a new node for the character
    public void put(char c, Node node) {
        links[c - 'a'] = node;
    }

    // Get the next node for the character
    public Node next(char c) {
        return links[c - 'a'];
    }
}

class Trie {

    private Node root;

    public Trie() {
        root = new Node();
    }

    // Insert a word into the Trie
    public void insert(String word) {
        Node node = root;
        for (char c : word.toCharArray()) {
            if (!node.contains(c)) {
                node.put(c, new Node());
            }
            node = node.next(c);
        }
    }

    // Check if the Trie contains a given prefix
    public boolean startsWith(String prefix) {
        Node node = root;
        for (char c : prefix.toCharArray()) {
            if (!node.contains(c)) {
                return false;
            }
            node = node.next(c);
        }
        return true;
    }
}

class Solution {

    public int countPrefixSuffixPairs(String[] words) {
        int n = words.length;
        int count = 0;

        // Step 1: Iterate over each word
        for (int i = 0; i < n; i++) {
            Trie prefixTrie = new Trie();
            Trie suffixTrie = new Trie();

            // Step 2: Insert the current word into the prefix Trie
            prefixTrie.insert(words[i]);

            // Step 3: Reverse the word and insert it into the suffix Trie
            String revWord = new StringBuilder(words[i]).reverse().toString();
            suffixTrie.insert(revWord);

            // Step 4: Iterate over all previous words
            for (int j = 0; j < i; j++) {
                // Step 5: Skip words[j] if it is longer than words[i]
                if (words[j].length() > words[i].length()) continue;

                // Step 6: Extract the prefix and reversed prefix of words[j]
                String prefixWord = words[j];
                String revPrefixWord = new StringBuilder(prefixWord)
                    .reverse()
                    .toString();

                // Step 7: Check if words[j] is both a prefix and suffix of words[i]
                if (
                    prefixTrie.startsWith(prefixWord) &&
                    suffixTrie.startsWith(revPrefixWord)
                ) {
                    count++;
                }
            }
        }

        // Step 8: Return the total count of valid pairs
        return count;
    }
}
