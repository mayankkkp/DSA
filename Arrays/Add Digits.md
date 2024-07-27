# 258. [Add Digits](https://leetcode.com/problems/add-digits/description/)

    class Solution:
    def addDigits(self, num: int) -> int:
        if num==0:
            return 0
        place=0
        ans=0
        while True:
            if place==1:
                return ans
            place=0
            ans=0
            while(num>0):
                d=num%10
                ans+=d
                place+=1
                num//=10
            num=ans
