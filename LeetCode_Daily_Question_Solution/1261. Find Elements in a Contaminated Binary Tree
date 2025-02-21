class FindElements {

    HashSet<Integer> seen;

    public FindElements(TreeNode root) {
        seen = new HashSet<>();
        bfs(root);
    }

    public boolean find(int target) {
        return seen.contains(target);
    }

    private void bfs(TreeNode root) {
        Queue<TreeNode> queue = new LinkedList<>();
        root.val = 0;
        queue.add(root);

        while (!queue.isEmpty()) {
            TreeNode currentNode = queue.remove();
            // visit currentNode by adding its recovered value to the set
            seen.add(currentNode.val);
            if (currentNode.left != null) {
                currentNode.left.val = currentNode.val * 2 + 1;
                queue.add(currentNode.left);
            }
            if (currentNode.right != null) {
                currentNode.right.val = currentNode.val * 2 + 2;
                queue.add(currentNode.right);
            }
        }
    }
}
