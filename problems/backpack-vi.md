# Backpack VI

## Problem

Given an integer array `nums` with all positive numbers and no duplicates, find the number of possible combinations that add up to a positive integer `target`.

## Example

Given `nums = [1, 2, 4]`, target = `4`

The possible combination ways are:

```
[1, 1, 1, 1]
[1, 1, 2]
[1, 2, 1]
[2, 1, 1]
[2, 2]
[4]
```

return `6`

## Code(Java)

```java
public class Solution {
    /**
     * @param nums   an integer array and all positive numbers, no duplicates
     * @param target an integer
     * @return an integer
     */
    public int backPackVI(int[] nums, int target) {
        // Write your code here
        int[] cnt = new int[target + 1];
        cnt[0] = 1;
        for (int i = 0; i <= target; i++) {
            if (cnt[i] == 0) continue;
            for (int j = 0; j < nums.length; j++) {
                if (i + nums[j] <= target) {
                    cnt[i + nums[j]] += cnt[i];
                }
            }
        }
        return cnt[target];
    }
}
```
