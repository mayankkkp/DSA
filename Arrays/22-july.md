# 53. Maximum Subarray

class Solution:
    def maxSubArray(self, nums: List[int]) -> int:
        sm=0
        mx=-sys.maxsize-1      
        for i in range(0,len(nums)):
            sm+=nums[i]

            if sm>mx:
                mx=sm
            # if mx<0:
            #     mx=0

            if sm<0:
                sum=0
        return mx  
