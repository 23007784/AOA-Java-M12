
# EX 2E Pattern Matching using KMP Algorithm.
## DATE: 16.09.25
## AIM:
To write a Java program for the following constraints.
Longest Palindromic Substring
Given a string s, return the longest palindromic substring in s.
using Manacher's Algorithm

## Algorithm
1. Start the program and import the required Java utility classes.
2. Read the number of test cases T from the user.
3. For each test case, input the text string and the pattern string.
4. Use a loop to slide the pattern over the text and compare each substring with the pattern.
5. Store all matching starting indices in a list and print them; if no match is found, print -1.

## Program:
```
/*
Program to implement Reverse a String
Developed by: NIKSHITHA G
Register Number: 212223110031
*/
import java.util.Scanner;

public class Solution {
    public String longestPalindrome(String s) {
        StringBuilder sPrime = new StringBuilder("#");
        for (char c : s.toCharArray()) {
            sPrime.append(c).append("#");
        }

        int n = sPrime.length();
        int[] palindromeRadii = new int[n];
        int center = 0;
        int radius = 0;

        for (int i = 0; i < n; i++) {
            int mirror = 2 * center - i;

            if (i < radius) {
                palindromeRadii[i] = Math.min(radius - i, palindromeRadii[mirror]);
            }

            while (
                i + 1 + palindromeRadii[i] < n &&
                i - 1 - palindromeRadii[i] >= 0 &&
                sPrime.charAt(i + 1 + palindromeRadii[i]) == sPrime.charAt(i - 1 - palindromeRadii[i])
            ) {
                palindromeRadii[i]++;
            }

            if (i + palindromeRadii[i] > radius) {
                center = i;
                radius = i + palindromeRadii[i];
            }
        }

        int maxLength = 0;
        int centerIndex = 0;
        for (int i = 0; i < n; i++) {
            if (palindromeRadii[i] > maxLength) {
                maxLength = palindromeRadii[i];
                centerIndex = i;
            }
        }

        int startIndex = (centerIndex - maxLength) / 2;
        return s.substring(startIndex, startIndex + maxLength);
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        //System.out.println("Enter a string:");
        String input = scanner.nextLine();

        Solution sol = new Solution();
        String result = sol.longestPalindrome(input);

        System.out.println("Longest Palindromic Substring: " + result);
        scanner.close();
    }
}

```

## Output:

<img width="834" height="192" alt="image" src="https://github.com/user-attachments/assets/7bed7eb1-fe4e-4660-8c47-8109a4a7313e" />

## Result:
The program successfully implemented and the expected output is verified.
