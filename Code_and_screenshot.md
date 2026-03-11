# 25MCI10232_ArnabLala_25MAM_KAR-1_practicalMSTCP

## Q1. 845. Longest Mountain in Array
```
class Solution 
{
    public int longestMountain(int[] arr) 
    {
        int n = arr.length;
        int maxsubarray = 0;
        for(int i = 1; i < n-1; i++) 
        {
            if(arr[i-1] < arr[i] && arr[i] > arr[i+1])
            {
                int left = i;
                int right = i;
                while(left > 0 && arr[left] > arr[left-1])
                {
                    left--;
                }
                while(right < n-1 && arr[right] > arr[right+1])
                {
                    right++;
                }
                maxsubarray = Math.max(maxsubarray , right-left+1);
            }           
        }
        return maxsubarray;
    }
}
```
<img width="1888" height="871" alt="image" src="https://github.com/user-attachments/assets/a89d01ca-2bca-4372-ac94-9af6249e085d" /><br>

## Q2 - 1760. Minimum Limit of Balls in a Bag
```
import java.util.*;

class Solution
{
    public int minimumSize(int[] nums, int maxOperations) 
    {
        
       
        PriorityQueue<Integer> pq = new PriorityQueue<>(Collections.reverseOrder());
        
        for(int i = 0; i < nums.length; i++){
            pq.add(nums[i]);
        }      
        while(maxOperations-- > 0){
            
            int largest = pq.poll();
            
            if(largest == 1){
                pq.add(largest);
                break;
            }
            
            int a = largest / 2;
            int b = largest - a;
            
            pq.add(a);
            pq.add(b);
        }
        
        return pq.peek();
    }
}
```
<img width="658" height="795" alt="image" src="https://github.com/user-attachments/assets/d09752c7-15a0-4203-a618-fc173341ace8" /><br>

