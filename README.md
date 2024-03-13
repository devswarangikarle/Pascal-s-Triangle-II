# Pascal-s-Triangle-II
Given an integer rowIndex, return the rowIndexth (0-indexed) row of the Pascal's triangle.  In Pascal's triangle, each number is the sum of the two numbers directly

from typing import List

class Solution:
    def getRow(self, rowIndex: int) -> List[int]:
        pascalTriangle = [[1]*(i+1) for i in range(rowIndex+1)]
        for row in range(2, rowIndex+1):
            for col in range(1, row):
                pascalTriangle[row][col] = pascalTriangle[row-1][col-1] + pascalTriangle[row-1][col]
        return pascalTriangle[rowIndex]
