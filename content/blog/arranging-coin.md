+++
author = "Rishabh"
title = "Aranging Coins"
date = "2020-04-03"
description = "441. Arranging Coins"
tags = ["leetcode"]
categories = ["leetcode"]
images  = ["img/2014/04/pic01.jpg"]
+++

You have a total of n coins that you want to form in a staircase shape, where every k-th row must have exactly k coins.

Given n, find the total number of full staircase rows that can be formed.

n is a non-negative integer and fits within the range of a 32-bit signed integer.

Example 1:

n = 5

The coins can form the following rows:
¤
¤ ¤
¤ ¤

Because the 3rd row is incomplete, we return 2.
Example 2:

n = 8

The coins can form the following rows:
¤
¤ ¤
¤ ¤ ¤
¤ ¤

Because the 4th row is incomplete, we return 3.

```
class Solution(object):
    def arrangeCoins(self, n):
        ans=0
        h=0
        i=0
        if(n==0):
            return 0
        elif(n<=2):
            return 1
        while(1):
            i+=1
            h=(i*(i+1))/2
            
            if(h>n):
                ans=i-1
                break
            elif(h==n):
                ans=i
                break
        return ans
```