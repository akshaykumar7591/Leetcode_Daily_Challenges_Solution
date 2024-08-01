class Solution {

    public int countSeniors(String[] details) {
        int seniorCount = 0;

        // Iterate through each passenger's details
        for (String passengerInfo : details) {
            // Extract the age from the passengerInfo string
            // Age is located at index 11 and 12 (2 characters)
            int age = Integer.parseInt(passengerInfo.substring(11, 13));

            // Check if the passenger is a senior (strictly over 60 years old)
            if (age > 60) {
                seniorCount++;
            }
        }

        return seniorCount;
    }
}
