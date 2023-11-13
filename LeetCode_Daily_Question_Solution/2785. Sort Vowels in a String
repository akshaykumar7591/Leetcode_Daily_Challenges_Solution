class Solution {
    public String sortVowels(String s) {
        // Step 1: Collect vowels and sort them in descending order
        List<Character> vowels = new ArrayList<>();
        for (char c : s.toCharArray()) {
            if ("aeiouAEIOU".indexOf(c) != -1) {
                vowels.add(c);
            }
        }
        Collections.sort(vowels, Collections.reverseOrder());

        // Step 2: Construct the answer string by replacing vowels in sorted order
        StringBuilder result = new StringBuilder();
        for (char c : s.toCharArray()) {
            if ("aeiouAEIOU".indexOf(c) != -1) {
                result.append(vowels.get(vowels.size() - 1));
                vowels.remove(vowels.size() - 1);
            } else {
                result.append(c);
            }
        }

        // Step 3: Return the final string
        return result.toString();        
    }
}
