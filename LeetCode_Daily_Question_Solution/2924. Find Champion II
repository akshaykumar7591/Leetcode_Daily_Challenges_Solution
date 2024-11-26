public class Solution {

    public int findChampion(int n, int[][] edges) {
        // Initialize the indegree array to track the number of incoming edges for each team
        int[] indegree = new int[n];

        // Store the indegree of each team
        for (int[] edge : edges) {
            indegree[edge[1]]++;
        }

        int champ = -1;
        int champCount = 0;

        // Iterate through all teams to find those with an indegree of 0
        for (int i = 0; i < n; i++) {
            // If the team can be a champion, store the team number and increment the count
            if (indegree[i] == 0) {
                champCount++;
                champ = i;
            }
        }

        // If more than one team can be a champion, return -1, otherwise return the champion team number
        return champCount > 1 ? -1 : champ;
    }
}
