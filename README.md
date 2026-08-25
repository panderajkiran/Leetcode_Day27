# Leetcode_Day27
# Day 27 — LeetCode 1832: Check if the Sentence Is Pangram

## Problem

Given a string containing lowercase English letters, determine whether it contains **every letter of the English alphabet at least once**.

## Approach

* Create a boolean array of size `26` to represent the English alphabet.
* For every character in the sentence, mark its corresponding position as `true`.
* Count how many unique letters were found.
* If all `26` letters are present, return `true`; otherwise, return `false`.

## Key Concept

The main idea is **character mapping**.

For a character `ch`, the index can be calculated using:

`ch - 'a'`

For example:

* `'a' - 'a' = 0`
* `'b' - 'a' = 1`
* `'z' - 'a' = 25`

This lets us efficiently track all 26 letters using a boolean array.

## Complexity

* **Time Complexity:** `O(n)`
* **Space Complexity:** `O(1)` because the array always has only 26 elements.

## What I Learned

This problem was a simple reminder that sometimes we don't need complicated data structures. A small fixed-size array can be enough to track unique characters efficiently.

## Solution

```java
class Solution {
    public boolean checkIfPangram(String sentence) {

        boolean[] visited = new boolean[26];

        for(char ch : sentence.toLowerCase().toCharArray()) {
            if(ch >= 'a' && ch <= 'z') {
                visited[ch - 'a'] = true;
            }
        }

        int count = 0;

        for(boolean b : visited) {
            if(b) count++;
        }

        return count == 26;
    }
}
```
