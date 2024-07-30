# 3233. [Find the Count of Numbers Which Are Not Special](https://leetcode.com/problems/find-the-count-of-numbers-which-are-not-special/description/)

    import math
    class Solution:
        def Nofprime(self, num):
            #seieve of eratosthenes
            prime=[True for i in range(num+1)]
            prime[0]=0
            prime[1]=0
    
            p=2
            while(p*p<=num):
                if prime[p]==True:
                    for i in range(p*p,num+1,p):
                        prime[i]=False
                p+=1
            
            #prefix sum for finding the no. of prime number upto some number
            for i in range(1,num+1):
                prime[i]+=prime[i-1]
    
            return prime
    
        def nonSpecialCount(self, l: int, r: int) -> int:
            left=int(math.sqrt(l))
            right=int(math.sqrt(r))
            # print(self.Nofprime(right),left,right)
    
            #we are increasing left because if we find sqrt of 5 we will get 3 , 
            # which can create error in our logic
            if(left*left!=l):
                left+=1
            prime=self.Nofprime(right)
            count=prime[right]-prime[left-1] #left-1 because we increased left earlier
    
            return (r-l)-count+1
    
            
    
