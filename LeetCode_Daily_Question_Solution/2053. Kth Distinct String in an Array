class Solution {

    public String kthDistinct(String[] arr, int k) {
        int n = arr.length;
        List<String> distinctStrings = new ArrayList<>();

        // Iterate through each string in the array
        for (int i = 0; i < n; i++) {
            String currentString = arr[i];
            boolean isDistinct = true;

            // Check if the current string is distinct
            for (int j = 0; j < n; j++) {
                if (j == i) continue; // Skip comparing with itself
                if (arr[j].equals(currentString)) {
                    isDistinct = false;
                    break;
                }
            }

            // If the string is distinct, add it to the list
            if (isDistinct) {
                distinctStrings.add(currentString);
            }
        }

        // Check if there are enough distinct strings
        if (distinctStrings.size() < k) {
            return "";
        }

        return distinctStrings.get(k - 1);
    }
}
