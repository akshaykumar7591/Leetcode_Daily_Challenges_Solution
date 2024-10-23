class Solution {

    public TreeNode replaceValueInTree(TreeNode root) {
        if (root == null) return root;

        Queue<TreeNode> nodeQueue = new LinkedList<>();
        nodeQueue.offer(root);
        List<Integer> levelSums = new ArrayList<>();

        // First BFS: Calculate sum of nodes at each level
        while (!nodeQueue.isEmpty()) {
            int levelSum = 0;
            int levelSize = nodeQueue.size();
            for (int i = 0; i < levelSize; ++i) {
                TreeNode currentNode = nodeQueue.poll();
                levelSum += currentNode.val;
                if (currentNode.left != null) nodeQueue.offer(currentNode.left);
                if (currentNode.right != null) nodeQueue.offer(
                    currentNode.right
                );
            }
            levelSums.add(levelSum);
        }

        // Second BFS: Update each node's value to sum of its cousins
        nodeQueue.offer(root);
        int levelIndex = 1;
        root.val = 0; // Root has no cousins
        while (!nodeQueue.isEmpty()) {
            int levelSize = nodeQueue.size();
            for (int i = 0; i < levelSize; ++i) {
                TreeNode currentNode = nodeQueue.poll();

                int siblingSum =
                    (currentNode.left != null ? currentNode.left.val : 0) +
                    (currentNode.right != null ? currentNode.right.val : 0);

                if (currentNode.left != null) {
                    currentNode.left.val = levelSums.get(levelIndex) -
                    siblingSum;
                    nodeQueue.offer(currentNode.left);
                }
                if (currentNode.right != null) {
                    currentNode.right.val = levelSums.get(levelIndex) -
                    siblingSum;
                    nodeQueue.offer(currentNode.right);
                }
            }
            ++levelIndex;
        }

        return root;
    }
}
