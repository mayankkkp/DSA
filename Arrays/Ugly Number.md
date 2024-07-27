# 263. [Ugly Number](https://leetcode.com/problems/ugly-number/description/)

    def isUgly(self, n: int) -> bool:
            if n<=0:
                return 0
            for num in [2,3,5]:
                while n%num==0:
                    n//=num
            if n==1:
                return 1
            return 0
