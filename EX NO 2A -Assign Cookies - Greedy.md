
# EX 2A Assign Cookies using Greedy Algorithm. 
## DATE: 26.08.25
## AIM:
To Write a Java program for the following Constraints.
Assume you are an awesome parent and want to give your children some cookies. But, you should give each child at most one cookie.

Each child i has a greed factor g[i], which is the minimum size of a cookie that the child will be content with; and each cookie j has a size s[j]. If s[j] >= g[i], we can assign the cookie j to the child i, and the child i will be content. Your goal is to maximise the number of your content children and output the maximum number.

## Algorithm
1. Start the program and import the Scanner and Arrays classes.
2. Read the number of children n and their greed factors into array g.
3. Read the number of cookies m and their sizes into array s.
4. Sort both arrays and use two pointers to compare greed and cookie size.
5. Count and display the maximum number of children who can be content with the available cookies. 

## Program:
```
/*
Program to implement Reverse a String
Developed by: NIKSHITHA G
Register Number: 212223110031 
*/
import java.util.*;

public class AssignCookies {
    
    public static int findContentChildren(int[] g, int[] s) {
        Arrays.sort(g);
        Arrays.sort(s);
        int i = 0, j = 0;
        while (i < g.length && j < s.length) {
            if (s[j] >= g[i]) i++;
            j++;
        }
        return i;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] g = new int[n];
        for (int i = 0; i < n; i++) g[i] = sc.nextInt();
        int m = sc.nextInt();
        int[] s = new int[m];
        for (int i = 0; i < m; i++) s[i] = sc.nextInt();
        System.out.println(findContentChildren(g, s));
    }
}
```

## Output:

<img width="326" height="329" alt="image" src="https://github.com/user-attachments/assets/db353c93-e94d-48b7-becb-5fd9fd04a360" />

## Result:
The program successfully print all the numbers from 1 to N. 
