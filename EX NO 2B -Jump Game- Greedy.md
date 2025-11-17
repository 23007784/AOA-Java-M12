
# EX 2B Jump Game using Greedy Algorithm.
## DATE: 02.09.25
## AIM:
To write a Java program to for given constraints.
You are given an array of integers. Each number represents the maximum number of steps you can jump forward from that position.

You start from the first element (index 0). 
Write a program to find the minimum number of jumps required to reach the last index of the array.

If it is not possible to reach the end, return -1.
## Algorithm
1. Start the program and import the Scanner class to take user input.
2. Read the size of the array n and input the array elements.
3. Initialize a variable maxReach to track the farthest index that can be reached.
4. Iterate through the array, updating maxReach and checking if the current index exceeds it.
5. If traversal completes without exceeding maxReach, print that the last index can be reached; otherwise, print false.  

## Program:
```
/*
Program to implement Reverse a String
Developed by: NIKSHITHA G
Register Number: 212223110031 
*/
import java.util.Scanner;

public class JumpGame {

    public static boolean canReachLastIndex(int[] nums) {
        int reachable = 0;
        for (int i = 0; i < nums.length; i++) {
            if (i > reachable) {
                return false;
            }
            reachable = Math.max(reachable, i + nums[i]);
        }
        return true;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt(); 
        int[] nums = new int[n];
        for (int i = 0; i < n; i++) {
            nums[i] = sc.nextInt();
        }

        System.out.println("Can reach last index: " + canReachLastIndex(nums));
    }
}

```

## Output:

<img width="728" height="231" alt="image" src="https://github.com/user-attachments/assets/5cca2c88-d5c7-4ee0-b43c-335d553dad13" />

## Result:
The program successfully implemented and the expected output is verified.
