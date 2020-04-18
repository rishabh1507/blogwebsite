+++
author = "Rishabh"
title = "Minimum Path Sum"
date = "2020-04-19"
description = " Minimum Path Sum "
tags = ["leetcode"]
categories = ["leetcode"]
images  = ["img/main/leetcode.jpg"]
+++
Given a m x n grid filled with non-negative numbers, find a path from top left to bottom right which minimizes the sum of all numbers along its path.

```
Input:
[
  [1,3,1],
  [1,5,1],
  [4,2,1]
]


Note: You can only move either down or right at any point in time.


Output: 7
Explanation: Because the path 1→3→1→1→1 minimizes the sum.

```

```
class Solution(object):
    def minPathSum(self, grid):
        """
        :type grid: List[List[int]]
        :rtype: int
        """
        rows = len(grid)
        cols = len(grid[0])
        
        min_path=[[0 for j in range(cols)] for i in range(rows)]
        
        for r in range(rows):
            for c in range(cols):
                if(r==0 and c==0):
                    min_path[r][c] = grid[0][0]
                else:
                    top = min_path[r-1][c] if r!=0 else float('inf')
                    left = min_path[r][c-1] if c!=0 else float('inf')
                        
                    min_path[r][c] = min(top,left) + grid[r][c]
                    
        return (min_path[rows-1][cols-1])
                        
                    
                    
                
```