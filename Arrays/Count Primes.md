# 204. [Count-Primes](https://leetcode.com/problems/count-primes/description/)

    class Solution:
    def countPrimes(self, n: int) -> int:
      if n==0 or n==1:
          return 0
      prime=[True for i in range(n)]
      prime[0]=0
      prime[1]=0
    
      p=2
      while(p*p<n):
          if prime[p]==True:
              for i in range(p*p,n,p):
                  prime[i]=False
          p+=1
      
      for i in range(1,n):
          prime[i]+=prime[i-1]
      # print(prime)
      
      return prime[n-1]
      
