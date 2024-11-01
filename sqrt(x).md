```java
class Solution {
    public int mySqrt(int x) {
        if(x <= 1) {
            return x;
        }
        
        //binary search where the target is between two numbers squared 
        
        int start = 1, end = (x/2)+1, sqrt = 0; 
        long mid = 0;

        while(start <= end) {
            mid = (start+end)/2;
            if(mid*mid == x) {
                return (int) mid;
            } else if(mid*mid < x) {
                start = (int) mid + 1;
                sqrt = (int) mid;
            } else {
                end = (int) mid - 1;
            }
        }

        return sqrt;
    }
}
```