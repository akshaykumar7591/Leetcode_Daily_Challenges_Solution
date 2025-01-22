public class Solution {

    public int[][] highestPeak(int[][] isWater) {
        int rows = isWater.length;
        int columns = isWater[0].length;
        final int INF = rows * columns; // Large value to represent uninitialized heights

        // Initialize the cellHeights matrix with INF (unprocessed cells)
        int[][] cellHeights = new int[rows][columns];
        for (int[] row : cellHeights) {
            Arrays.fill(row, INF);
        }

        // Set the height of water cells to 0
        for (int row = 0; row < rows; row++) {
            for (int col = 0; col < columns; col++) {
                if (isWater[row][col] == 1) {
                    cellHeights[row][col] = 0; // Water cells have height 0
                }
            }
        }

        // Forward pass: updating heights based on top and left neighbors
        for (int row = 0; row < rows; row++) {
            for (int col = 0; col < columns; col++) {
                int minNeighborDistance = INF; // Initialize minimum neighbor distance

                // Check the cell above
                int neighborRow = row - 1;
                int neighborCol = col;
                if (isValidCell(neighborRow, neighborCol, rows, columns)) {
                    minNeighborDistance = Math.min(
                        minNeighborDistance,
                        cellHeights[neighborRow][neighborCol]
                    );
                }

                // Check the cell to the left
                neighborRow = row;
                neighborCol = col - 1;
                if (isValidCell(neighborRow, neighborCol, rows, columns)) {
                    minNeighborDistance = Math.min(
                        minNeighborDistance,
                        cellHeights[neighborRow][neighborCol]
                    );
                }

                // Set the current cell's height as the minimum of its neighbors + 1
                cellHeights[row][col] = Math.min(
                    cellHeights[row][col],
                    minNeighborDistance + 1
                );
            }
        }

        // Backward pass: updating heights based on bottom and right neighbors
        for (int row = rows - 1; row >= 0; row--) {
            for (int col = columns - 1; col >= 0; col--) {
                int minNeighborDistance = INF; // Initialize minimum neighbor distance

                // Check the cell below
                int neighborRow = row + 1;
                int neighborCol = col;
                if (isValidCell(neighborRow, neighborCol, rows, columns)) {
                    minNeighborDistance = Math.min(
                        minNeighborDistance,
                        cellHeights[neighborRow][neighborCol]
                    );
                }

                // Check the cell to the right
                neighborRow = row;
                neighborCol = col + 1;
                if (isValidCell(neighborRow, neighborCol, rows, columns)) {
                    minNeighborDistance = Math.min(
                        minNeighborDistance,
                        cellHeights[neighborRow][neighborCol]
                    );
                }

                // Set the current cell's height as the minimum of its neighbors + 1
                cellHeights[row][col] = Math.min(
                    cellHeights[row][col],
                    minNeighborDistance + 1
                );
            }
        }

        return cellHeights; // Return the calculated cell heights
    }

    // Function to check if a cell is within grid bounds
    private boolean isValidCell(int row, int col, int rows, int columns) {
        return row >= 0 && col >= 0 && row < rows && col < columns;
    }
}
