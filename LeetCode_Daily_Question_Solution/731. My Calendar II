class MyCalendarTwo {

    private List<int[]> bookings;
    private List<int[]> overlapBookings;

    // Return true if the booking [start1, end1) & [start2, end2) overlaps.
    private boolean doesOverlap(int start1, int end1, int start2, int end2) {
        return Math.max(start1, start2) < Math.min(end1, end2);
    }

    // Return overlapping booking between [start1, end1) & [start2, end2).
    private int[] getOverlapped(int start1, int end1, int start2, int end2) {
        return new int[] { Math.max(start1, start2), Math.min(end1, end2) };
    }

    public MyCalendarTwo() {
        bookings = new ArrayList<>();
        overlapBookings = new ArrayList<>();
    }

    public boolean book(int start, int end) {
        // Returns false if the new booking has an overlap
        // with the existing double-booked bookings.
        for (int[] booking : overlapBookings) {
            if (doesOverlap(booking[0], booking[1], start, end)) {
                return false;
            }
        }

        // Add the double overlapping bookings if any with the new booking.
        for (int[] booking : bookings) {
            if (doesOverlap(booking[0], booking[1], start, end)) {
                overlapBookings.add(
                    getOverlapped(booking[0], booking[1], start, end)
                );
            }
        }

        // Add the new booking to the list of bookings.
        bookings.add(new int[] { start, end });
        return true;
    }
}
