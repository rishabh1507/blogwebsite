+++
author = "Rishabh"
title = "Number of island"
date = "2020-04-17"
description = " Day 16 of challenge"
tags = ["leetcode30day"]
categories = ["leetcode"]
images  = ["img/2014/04/pic01.jpg"]
+++

Given a 2d grid map of '1's (land) and '0's (water), count the number of islands. An island is surrounded by water and is formed by connecting adjacent lands horizontally or vertically. You may assume all four edges of the grid are all surrounded by water.

Example 1:

Input:
11110
11010
11000
00000

Output: 1

```
class Solution(object):
    def numIslands(self, grid):
        """
        :type grid: List[List[str]]
        :rtype: int
        """
        island=0
        for i in range(len(grid)):
            for j in range(len(grid[i])):
                if (grid[i][j] == "1"):
                    island+=1
                    self.helper(grid,i,j)
        
        return island
    
    def helper(self,grid,i,j):
        if(i<0 or j<0 or i>=len(grid) or j>=len(grid[i]) or grid[i][j]!="1"):
            return
        else:
            grid[i][j]="0"
            self.helper(grid,i+1,j)
            self.helper(grid,i-1,j)
            self.helper(grid,i,j+1)
            self.helper(grid,i,j-1)
```