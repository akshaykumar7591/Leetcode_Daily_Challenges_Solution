class Solution {

    static class Point {

        int x;
        int y;

        Point(int x, int y) {
            this.x = x;
            this.y = y;
        }

        @Override
        public boolean equals(Object o) {
            if (this == o) {
                return true;
            }
            if (o == null || getClass() != o.getClass()) {
                return false;
            }
            Point point = (Point) o;
            return x == point.x && y == point.y;
        }

        @Override
        public int hashCode() {
            return Objects.hash(x, y);
        }
    }

    public int numberOfPairs(int[][] points) {
        Map<Integer, Integer> col = new HashMap<>();
        Map<Integer, Integer> row = new HashMap<>();
        Map<Point, int[]> coordinatesMap = new HashMap<>();

        for (int[] point : points) {
            int x = point[0];
            int y = point[1];
            col.put(x, 0);
            row.put(y, 0);
        }
        List<Integer> colKeys = new ArrayList<>(col.keySet());
        Collections.sort(colKeys);
        for (int i = 0; i < colKeys.size(); i++) {
            col.put(colKeys.get(i), i + 1);
        }
        List<Integer> rowKeys = new ArrayList<>(row.keySet());
        Collections.sort(rowKeys);
        for (int i = 0; i < rowKeys.size(); i++) {
            row.put(rowKeys.get(i), i + 1);
        }

        int nc = col.size() + 1;
        int nr = row.size() + 1;
        int[][] m = new int[nc][nr];
        int[][] prefixSum = new int[nc][nr];

        for (int[] point : points) {
            int x = point[0];
            int y = point[1];
            int c = col.get(x);
            int r = row.get(y);
            Point key = new Point(x, y);
            coordinatesMap.put(key, new int[] { c, r });
            m[c][r] = 1;
        }
        for (int i = 1; i < nc; i++) {
            for (int j = 1; j < nr; j++) {
                prefixSum[i][j] =
                    prefixSum[i - 1][j] +
                    prefixSum[i][j - 1] -
                    prefixSum[i - 1][j - 1] +
                    m[i][j];
            }
        }

        int ans = 0;
        Arrays.sort(points, (a, b) -> {
            if (a[0] == b[0]) {
                return Integer.compare(b[1], a[1]);
            }
            return Integer.compare(a[0], b[0]);
        });

        int n = points.length;
        for (int i = 0; i < n - 1; i++) {
            for (int j = i + 1; j < n; j++) {
                if (points[i][1] >= points[j][1]) {
                    Point key1 = new Point(points[i][0], points[i][1]);
                    Point key2 = new Point(points[j][0], points[j][1]);
                    int[] coord1 = coordinatesMap.get(key1);
                    int[] coord2 = coordinatesMap.get(key2);
                    int c1 = coord1[0];
                    int r1 = coord1[1];
                    int c2 = coord2[0];
                    int r2 = coord2[1];
                    int cnt =
                        prefixSum[c2][r1] -
                        prefixSum[c1 - 1][r1] -
                        prefixSum[c2][r2 - 1] +
                        prefixSum[c1 - 1][r2 - 1];
                    if (cnt == 2) {
                        ans++;
                    }
                }
            }
        }

        return ans;
    }
}
