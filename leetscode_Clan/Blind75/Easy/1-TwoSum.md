# 1. Two Sum

Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.
You may assume that each input would have exactly one solution, and you may not use the same element twice.
You can return the answer in any order.

## Example 1:
Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].

## Example 2:
Input: nums = [3,2,4], target = 6
Output: [1,2]

## Example 3:
Input: nums = [3,3], target = 6
Output: [0,1]
 
## Constraints:
* 2 <= nums.length <= 104
* -109 <= nums[i] <= 109
* -109 <= target <= 109
* Only one valid answer exists.
 
## Recommended Time & Space Complexity
You should aim for a solution with O(n + m) time and O(1) space, where n is the length of the string s and m is the length of the string t.
Follow-up: Can you come up with an algorithm that is less than O(n2) time complexity?

# 1. Sorting
```
# Python
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        if len(s) != len(t):
            return False
            
        return sorted(s) == sorted(t)
```
```
# Java
public class Solution {
    public boolean isAnagram(String s, String t) {
        if (s.length() != t.length()) {
            return false;
        }

        char[] sSort = s.toCharArray();
        char[] tSort = t.toCharArray();
        Arrays.sort(sSort);
        Arrays.sort(tSort);
        return Arrays.equals(sSort, tSort);
    }
}
```
## Time & Space Complexity
Time complexity: O(nlogn + mlogm)
Space complexity: O(n+m) depending on the sorting algorithm.

Where 
n is the length of string s and m is the length of string t.

#

# Links
https://neetcode.io/solutions/two-sum
https://leetcode.com/problems/two-sum/description/
