# 53. [Rotate-image](https://leetcode.com/problems/rotate-image/description/)


    

    class Solution:
    def rotate(self, matrix: List[List[int]]) -> None:
        """
        Do not return anything, modify matrix in-place instead.
        """
        # d={}
        for i in range(len(matrix)):
            for j in range(0,i):
                matrix[i][j],matrix[j][i]=matrix[j][i],matrix[i][j]
                # print(matrix)
        
        for i in range(len(matrix)):
            matrix[i]=matrix[i][::-1]
        
