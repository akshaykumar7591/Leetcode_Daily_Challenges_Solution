class Solution {

    public String getDirections(TreeNode root, int startValue, int destValue) {
        // Map to store parent nodes
        Map<Integer, TreeNode> parentMap = new HashMap<>();

        // Find the start node and populate parent map
        TreeNode startNode = findStartNode(root, startValue);
        populateParentMap(root, parentMap);

        // Perform BFS to find the path
        Queue<TreeNode> queue = new LinkedList<>();
        queue.add(startNode);
        Set<TreeNode> visitedNodes = new HashSet<>();
        // Key: next node, Value: <current node, direction>
        Map<TreeNode, Pair<TreeNode, String>> pathTracker = new HashMap<>();
        visitedNodes.add(startNode);

        while (!queue.isEmpty()) {
            TreeNode currentNode = queue.poll();

            // If destination is reached, return the path
            if (currentNode.val == destValue) {
                return backtrackPath(currentNode, pathTracker);
            }

            // Check and add parent node
            if (parentMap.containsKey(currentNode.val)) {
                TreeNode parentNode = parentMap.get(currentNode.val);
                if (!visitedNodes.contains(parentNode)) {
                    queue.add(parentNode);
                    pathTracker.put(parentNode, new Pair(currentNode, "U"));
                    visitedNodes.add(parentNode);
                }
            }

            // Check and add left child
            if (
                currentNode.left != null &&
                !visitedNodes.contains(currentNode.left)
            ) {
                queue.add(currentNode.left);
                pathTracker.put(currentNode.left, new Pair(currentNode, "L"));
                visitedNodes.add(currentNode.left);
            }

            // Check and add right child
            if (
                currentNode.right != null &&
                !visitedNodes.contains(currentNode.right)
            ) {
                queue.add(currentNode.right);
                pathTracker.put(currentNode.right, new Pair(currentNode, "R"));
                visitedNodes.add(currentNode.right);
            }
        }

        // This line should never be reached if the tree is valid
        return "";
    }

    private String backtrackPath(
        TreeNode node,
        Map<TreeNode, Pair<TreeNode, String>> pathTracker
    ) {
        StringBuilder path = new StringBuilder();

        // Construct the path
        while (pathTracker.containsKey(node)) {
            // Add the directions in reverse order and move on to the previous node
            path.append(pathTracker.get(node).getValue());
            node = pathTracker.get(node).getKey();
        }

        // Reverse the path
        path.reverse();

        return path.toString();
    }

    private void populateParentMap(
        TreeNode node,
        Map<Integer, TreeNode> parentMap
    ) {
        if (node == null) return;

        // Add children to the map and recurse further
        if (node.left != null) {
            parentMap.put(node.left.val, node);
            populateParentMap(node.left, parentMap);
        }

        if (node.right != null) {
            parentMap.put(node.right.val, node);
            populateParentMap(node.right, parentMap);
        }
    }

    private TreeNode findStartNode(TreeNode node, int startValue) {
        if (node == null) return null;

        if (node.val == startValue) return node;

        TreeNode leftResult = findStartNode(node.left, startValue);

        // If left subtree returns a node, it must be StartNode. Return it
        // Otherwise, return whatever is returned by right subtree.
        if (leftResult != null) return leftResult;
        return findStartNode(node.right, startValue);
    }
}
