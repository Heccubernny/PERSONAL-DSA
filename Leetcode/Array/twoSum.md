Problem name: Two sum
-

Level: easy
-

Data Structure Used: Array
-

Algorithms Used: Brute force
-

Language Used: Python 3.10
-

Big(O):

- Time Complexity: O(n^2)
- Space Complexity: O(n)

Problem: Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order
-

Solution:

class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
       n: int = len(nums)
       for i in range(n):
           for j in range(i + 1, n):
               if nums[j] == target - nums[i]:
                   return[i, j]

rt = Solution()

res: int = rt.twoSum([2,7,11,15], 9)

print(res)


<!-- Other suggestion -->

Follow-up: Can you come up with an algorithm that is less than O(n2) time complexity?

We can make use of an another algorithm that is less than O(n^2) time complexity.

Using One Pass HashTable

class Solution:
    def twoSum(self, nums, target):
        hm = {} <!-- Create an empty hashmap to store-->
        n = len(nums)
        for i in range(n): <!-- iterate over nums using it's index number-->
            c = target - nums[i] <!-- 22 - 2 = 20 -->
            if c in hm: <!-- C is not in the hashmap --> <!--if the current C exist in the hashmap-->
                return [i, hm[c]] <!-- skip index of 0 --> <!--The sum is found and it return the indices (two index)immediately -->
            hm[nums[i]] = i <!-- save our array nums index and value into hashmap in form of "value": index i.e "2": 0 --> <!-- Follow the process to iterate -->




r = Solution()
res = r.twoSum([2, 7, 11, 15], 22)

print(res)
