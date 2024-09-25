class TrieNode {

    TrieNode[] next = new TrieNode[26];
    int cnt = 0;
}

class Solution {

    // Initialize the root node of the trie.
    TrieNode root = new TrieNode();

    // Insert function for the word.
    void insert(String word) {
        TrieNode node = root;
        for (char c : word.toCharArray()) {
            // If new prefix, create a new trie node.
            if (node.next[c - 'a'] == null) {
                node.next[c - 'a'] = new TrieNode();
            }
            // Increment the count of the current prefix.
            node.next[c - 'a'].cnt++;
            node = node.next[c - 'a'];
        }
    }

    // Calculate the prefix count using this function.
    int count(String s) {
        TrieNode node = root;
        int ans = 0;
        // The ans would store the total sum of counts.
        for (char c : s.toCharArray()) {
            ans += node.next[c - 'a'].cnt;
            node = node.next[c - 'a'];
        }
        return ans;
    }

    public int[] sumPrefixScores(String[] words) {
        int N = words.length;
        // Insert words in trie.
        for (int i = 0; i < N; i++) {
            insert(words[i]);
        }
        int[] scores = new int[N];
        for (int i = 0; i < N; i++) {
            // Get the count of all prefixes of given string.
            scores[i] = count(words[i]);
        }
        return scores;
    }
}
