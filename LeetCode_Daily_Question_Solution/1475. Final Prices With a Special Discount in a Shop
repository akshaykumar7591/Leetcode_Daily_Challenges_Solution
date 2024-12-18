class Solution {

    public int[] finalPrices(int[] prices) {
        // Create a copy of prices array to store discounted prices
        int[] result = prices.clone();

        Stack<Integer> stack = new Stack<>();

        for (int i = 0; i < prices.length; i++) {
            // Process items that can be discounted by current price
            while (!stack.isEmpty() && prices[stack.peek()] >= prices[i]) {
                // Apply discount to previous item using current price
                result[stack.pop()] -= prices[i];
            }
            // Add current index to stack
            stack.add(i);
        }

        return result;
    }
}
