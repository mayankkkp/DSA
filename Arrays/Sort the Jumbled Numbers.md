# 2191. [Sort the Jumbled Numbers](https://leetcode.com/problems/sort-the-jumbled-numbers/description/)

    class Solution:
      def sortJumbled(self, mapping: List[int], nums: List[int]) -> List[int]:
          def map(mapping: List[int],num):
              if num==0:
                  return mapping[0]
              res=0
              place=0
              n=num
              while(n>0):
                  d=n%10
                  newd=mapping[d]
                  res=newd*pow(10,place)+res
                  n=n//10
                  place+=1
              return res
          ans=[]
          for idx,num in enumerate(nums):
              #enumerate function gives accessibility to store element with its index
              #we can choose user index too
              ans.append((map(mapping,num),idx,num))
          ans.sort()
          for i in range(len(nums)):
              nums[i]=ans[i][2]
          return nums
        
