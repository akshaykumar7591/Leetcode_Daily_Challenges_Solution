public class Solution {
    public int eliminateMaximum(int[] dist, int[] speed) {
        int n = dist.length;
        double[] time_to_city = new double[n];
        
        for (int i = 0; i < n; i++) {
            time_to_city[i] = (double)dist[i] / speed[i];
        }
        
        Arrays.sort(time_to_city);
        
        for (int i = 0; i < n; i++) {
            if (time_to_city[i] <= i) {
                return i;
            }
        }
        
        return n;
    }
}
