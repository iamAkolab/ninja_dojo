# 217. Contains Duplicate.....
Given an integer array nums, return true if any value appears at least twice in the array, and return false if every element is distinct.

## Example 1:
* Input: nums = [1,2,3,1]
* Output: true

Explanation:
The element 1 occurs at the indices 0 and 3.

## Example 2:
* Input: nums = [1,2,3,4]
* Output: false

Explanation:
All elements are distinct.

## Example 3:

Input: nums = [1,1,1,3,3,4,3,2,4,2]
Output: true

 

## Constraints:

* 1 <= nums.length <= 105
* -109 <= nums[i] <= 109

## Recommended Time & Space Complexity
You should aim for a solution with O(n) time and O(n) space, where n is the size of the input array.


## 1. Brute Force
```
# Python
class Solution:
    def hasDuplicate(self, nums: List[int]) -> bool:
        for i in range(len(nums)):
            for j in range(i + 1, len(nums)):
                if nums[i] == nums[j]:
                    return True
        return False
```

```
# Java
public class Solution {
    public boolean hasDuplicate(int[] nums) {
        for (int i = 0; i < nums.length; i++) {
            for (int j = i + 1; j < nums.length; j++) {
                if (nums[i] == nums[j]) {
                    return true;
                }
            }
        }
        return false;
    }
}
```

### Time & Space Complexity
* Time complexity: O(n^2)
* Space complexity: O(1)

## 2. Sorting
```
# Python
class Solution:
    def hasDuplicate(self, nums: List[int]) -> bool:
        nums.sort()
        for i in range(1, len(nums)):
            if nums[i] == nums[i - 1]:
                return True
        return False
```
```
# Java
public class Solution {
    public boolean hasDuplicate(int[] nums) {
        Arrays.sort(nums);
        for (int i = 1; i < nums.length; i++) {
            if (nums[i] == nums[i - 1]) {
                return true;
            }
        }
        return false;
    }
}
```
### Time & Space Complexity
* Time complexity: O(nlogn)
* Space complexity: O(1) or O(n) depending on the sorting algorithm.

# 3. Hash Set
```
# Python
class Solution:
    def hasDuplicate(self, nums: List[int]) -> bool:
        seen = set()
        for num in nums:
            if num in seen:
                return True
            seen.add(num)
        return False
```
```
# Java
public class Solution {
    public boolean hasDuplicate(int[] nums) {
        Set<Integer> seen = new HashSet<>();
        for (int num : nums) {
            if (seen.contains(num)) {
                return true;
            }
            seen.add(num);
        }
        return false;
    }
}
```
### Time & Space Complexity
* Time complexity: O(n)
* Space complexity: O(n)

# 4. Hash Set Length
```
# Python
class Solution:
    def hasDuplicate(self, nums: List[int]) -> bool:
        return len(set(nums)) < len(nums)e
```
```
# Java
public class Solution {
    public boolean hasDuplicate(int[] nums) {
        return Arrays.stream(nums).distinct().count() < nums.length;
    }
}
```
### Time & Space Complexity
* Time complexity: O(n)
* Space complexity: O(n)
  
# Links
* https://neetcode.io/solutions/contains-duplicate
* https://leetcode.com/problems/contains-duplicate/description/
