Best Leetcode problems for strings.

A guide to prepare gradually:

🟢 20 Easy
🟠 20 Medium
🔴 8 Hard
⚫ tips and patterns to solve strings problems

[ THREAD ] ↓

Short disclaimer.

This is a selection of my favourite problems concerning strings.

I tackled them and I think everyone can improve by gradually solving them.

I tried to put only string related problems, but some advanced ones require knowledge of topics like DP & tries. 🟢 Easy

8 String to Integer (atoi)
13 Roman to Integer
28 Implement strStr()
67 Add Binary
125Valid Palindrome
168 Excel Sheet Column Title
171 Excel Sheet Column Number
205 Isomorphic Strings
242 Valid Anagram
344 Reverse String
387 First Unique Character in a String

392Is Subsequence
412Fizz Buzz
415 Add Strings
796Rotate String
844Backspace String Compare
953Verifying an Alien Dictionary
1002 Find Common Characters
1047 Remove All Adjacent Duplicates In String
1446 Consecutive Characters

🟠 Medium

3 Longest Substring Without Repeating Character
5 Longest Palindromic Substring
6 Zigzag Conversion
8 String to Integer (atoi)
12 Integer to Roman
17 Letter Combinations of a Phone Number
22 Generate Parentheses
38 Count and Say
43 Multiply Strings
71 Simplify Path

93 Restore IP Addresses
151 Reverse Words in a String
165 Compare Version Numbers
271 Encode and Decode Strings
316 Remove Duplicate Letters
394 Decode String
767 Reorganize String
1041 Robot Bounded In Circle
1268 Search Suggestions System
1396 Design Underground System

🔴 Hard

10. Regular Expression Matching
68 Text Justification
72 Edit Distance
76 Minimum Window Substring
127 Word Ladder
269 Alien Dictionary
273 Integer to English Word
726 Number of Atoms

⚫ Tips and Patterns

1. Take advantage that you can access efficiently both ends of a string and use 2 pointers technique

2. Often brute force solution use O(n) space, but it's usually possible optimize to O(1)

Instead of storing characters into a hash table, try to use a 256 fixed-length array. This simplifies the code and makes transparent the used amount of space

4. Languages like C# and Java provide a StringBuilder class to efficiently concatenate strings. Make use of it. Strings are immutable in many programming languages. Consider this when concatenating strings and learn to use alternatives like arrays/lists of chars.

6. Rolling hash is a specific technique used for string comparison. It's useful to efficiently solve some tricky problems. Learn how to refer to characters by their ASCII values, this is very common. For example how to:

• Get the ASCII value of a character
• Convert an ASCII value into a character
• Convert a digit character into its integer value

Sliding windows are a technique that come up a lot. It usually makes possible to improve the time complexity from quadratic to linear.

9. Learn how to implement tries for representing and storing a set of words. They are useful to solve advanced problems.
