# 56. [Merge Intervals]([https://leetcode.com/problems/maximum-subarray/description/](https://leetcode.com/problems/merge-intervals/description/))


    

    class Solution:
    def merge(self, intervals: List[List[int]]) -> List[List[int]]:
        ans=[]
        intervals.sort()
        for i in intervals:
            start=i[0]
            end=i[1]
            if len(ans)!=0 and start<=ans[-1][1]:
                ans[-1][1]=max(end,ans[-1][1])
            else:
                ans.append([start,end])
        return ans
