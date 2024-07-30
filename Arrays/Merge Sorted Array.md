# 88. [Merge Sorted Array](https://leetcode.com/problems/merge-sorted-array/description/)

    class Solution:
        def merge(self, nums1: List[int], m: int, nums2: List[int], n: int) -> None:
            """
            Do not return anything, modify nums1 in-place instead.
            """
            idx1=m-1
            idx2=n-1
            cur=m+n-1
    
            while(idx2>=0):
                if(idx1>=0 and nums1[idx1]>nums2[idx2]):
                    nums1[cur]=nums1[idx1]
                    cur-=1
                    idx1-=1
                else:
                    nums1[cur]=nums2[idx2]
                    cur-=1
                    idx2-=1
        
