class Solution {

    public int nthUglyNumber(int n) {
        TreeSet<Long> uglyNumbersSet = new TreeSet<>(); // TreeSet to store potential ugly numbers
        uglyNumbersSet.add(1L); // Start with 1, the first ugly number
        // TreeSet automatically sorts elements in ascending order and does not
        // allow duplicate entries, just like a HashSet in python

        Long currentUgly = 1L;
        for (int i = 0; i < n; i++) {
            currentUgly = uglyNumbersSet.pollFirst(); // Get the smallest number from the set and remove it

            // Insert the next potential ugly numbers into the set
            uglyNumbersSet.add(currentUgly * 2);
            uglyNumbersSet.add(currentUgly * 3);
            uglyNumbersSet.add(currentUgly * 5);
        }

        return currentUgly.intValue(); // Return the nth ugly number
    }
}
