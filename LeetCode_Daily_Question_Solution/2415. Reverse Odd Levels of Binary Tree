class Solution {

    public TreeNode reverseOddLevels(TreeNode root) {
        if (root == null) {
            return null; // Return null if the tree is empty.
        }

        Queue<TreeNode> queue = new LinkedList<>();
        queue.add(root); // Start BFS with the root node.
        int level = 0;

        while (!queue.isEmpty()) {
            int size = queue.size();
            List<TreeNode> currentLevelNodes = new ArrayList<>();

            // Process all nodes at the current level.
            for (int i = 0; i < size; i++) {
                TreeNode node = queue.poll();
                currentLevelNodes.add(node);

                if (node.left != null) queue.add(node.left);
                if (node.right != null) queue.add(node.right);
            }

            // Reverse node values if the current level is odd.
            if (level % 2 == 1) {
                int left = 0, right = currentLevelNodes.size() - 1;
                while (left < right) {
                    int temp = currentLevelNodes.get(left).val;
                    currentLevelNodes.get(left).val = currentLevelNodes.get(
                        right
                    ).val;
                    currentLevelNodes.get(right).val = temp;
                    left++;
                    right--;
                }
            }

            level++;
        }

        return root; // Return the modified tree root.
    }
}
