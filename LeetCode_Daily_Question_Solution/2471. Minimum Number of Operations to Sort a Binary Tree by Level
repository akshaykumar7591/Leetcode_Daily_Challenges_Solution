class Solution {

    // Constants for bit manipulation
    final int SHIFT = 20;
    final int MASK = 0xFFFFF;

    public int minimumOperations(TreeNode root) {
        Queue<TreeNode> queue = new LinkedList();
        queue.add(root);
        int swaps = 0;

        // Process tree level by level using BFS
        while (!queue.isEmpty()) {
            int levelSize = queue.size();
            long[] nodes = new long[levelSize];

            // Store node values with encoded positions
            for (int i = 0; i < levelSize; i++) {
                TreeNode node = queue.poll();
                // Encode value and index: high 20 bits = value, low 20 bits = index
                nodes[i] = ((long) node.val << SHIFT) + i;

                if (node.left != null) queue.add(node.left);
                if (node.right != null) queue.add(node.right);
            }

            // Sort nodes by their values (high 20 bits)
            Arrays.sort(nodes);

            // Count swaps needed to match indices with original positions
            for (int i = 0; i < levelSize; i++) {
                int origPos = (int) (nodes[i] & MASK);
                if (origPos != i) {
                    // Swap nodes and decrement i to recheck current position
                    long temp = nodes[i];
                    nodes[i--] = nodes[origPos];
                    nodes[origPos] = temp;
                    swaps++;
                }
            }
        }
        return swaps;
    }
}
