#Concatenation of Array

You are given an integer array nums of length n. Create an array ans of length 2n where ans[i] == nums[i] and ans[i + n] == nums[i] for 0 <= i < n (0-indexed).

Specifically, ans is the concatenation of two nums arrays.

Return the array ans.

Example 1:

Input: nums = [1,4,1,2]

Output: [1,4,1,2,1,4,1,2]
Example 2:

Input: nums = [22,21,20,1]

Output: [22,21,20,1,22,21,20,1]


***ANSWER***

---class Solution {
---    public int[] getConcatenation(int[] nums) {
---       int n=nums.length;
---        int k=0;
---        int con[]=new int[nums.length];
---        for(int i=0;i<nums.length;i++)
---        {
---        con[i]=nums[i];    
---        }
---        int ans[]=new int[n*2];
---        for(int i=0;i<ans.length;i++)
---        {
---           if(i<nums.length)
---            {
---                ans[i]=nums[i];
---            }
---           else
---            {
---                ans[i]=con[k];
---                k++;
---           }
---        }
---        return ans;
---    }
}
