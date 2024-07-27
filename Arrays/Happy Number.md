# 202. [Happy Number](https://leetcode.com/problems/happy-number/description/)

    class Solution:
      def isHappy(self, n: int) -> bool:
          calculated={}
          ans=0
          num=n
          while True:
              # print(calculated,ans,num)
              if num==1:
                  return 1
              if num in calculated:
                  return 0
              calculated[num]=0
              while(num>0):
                  d=num%10
                  ans+=pow(d,2)
                  num=num//10
              num=ans
              ans=0
        

        
