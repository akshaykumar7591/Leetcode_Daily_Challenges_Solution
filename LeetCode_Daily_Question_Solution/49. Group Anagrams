

class Solution {
    public List<List<String>> groupAnagrams(String[] strs) {
        Map<String, Integer> mp = new HashMap<>();
        List<List<String>> ans = new ArrayList<>();

        for (String str : strs) {
            char[] chars = str.toCharArray();
            Arrays.sort(chars);
            String sortedStr = new String(chars);
            
            if (mp.containsKey(sortedStr)) {
                ans.get(mp.get(sortedStr)).add(str);
            } else {
                mp.put(sortedStr, ans.size());
                ans.add(new ArrayList<>(Arrays.asList(str)));
            }
        }

        return ans;
    }
}

