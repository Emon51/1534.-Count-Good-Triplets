# 1534.-Count-Good-Triplets
Practicing Nested Loop.

class Solution:
    def countGoodTriplets(self, arr: List[int], a: int, b: int, c: int) -> int:
      """
      count=0
      n=len(arr)
      for i in range(n-2):
        for j in range(i+1,n-1):
          for k in range(j+1,n):
            x=abs(arr[i]-arr[j])<=a
            y=abs(arr[j]-arr[k])<=b
            z=abs(arr[i]-arr[k])<=c
            
            if all((x,y,z)):#or if all([x,y,z])
              count+=1
              
      return count
      """
      n=len(arr)
      def helper(i,j,k):
        x=abs(arr[i]-arr[j])<=a
        y=abs(arr[j]-arr[k])<=b
        z=abs(arr[i]-arr[k])<=c
        return all((x,y,z))
      
      return sum(1 for i in range(n-2) for j in range(i+1,n-1) for k in range(j+1,n) if helper(i,j,k))
        
        
        
        
