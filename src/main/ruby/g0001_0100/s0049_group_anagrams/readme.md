[![](https://img.shields.io/github/stars/LeetCode-in-Ruby/LeetCode-in-Ruby?label=Stars&style=flat-square)](https://github.com/LeetCode-in-Ruby/LeetCode-in-Ruby)
[![](https://img.shields.io/github/forks/LeetCode-in-Ruby/LeetCode-in-Ruby?label=Fork%20me%20on%20GitHub%20&style=flat-square)](https://github.com/LeetCode-in-Ruby/LeetCode-in-Ruby/fork)

## 49\. Group Anagrams

Medium

Given an array of strings `strs`, group **the anagrams** together. You can return the answer in **any order**.

An **Anagram** is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

**Example 1:**

**Input:** strs = ["eat","tea","tan","ate","nat","bat"]

**Output:** [["bat"],["nat","tan"],["ate","eat","tea"]] 

**Example 2:**

**Input:** strs = [""]

**Output:** [[""]] 

**Example 3:**

**Input:** strs = ["a"]

**Output:** [["a"]] 

**Constraints:**

*   <code>1 <= strs.length <= 10<sup>4</sup></code>
*   `0 <= strs[i].length <= 100`
*   `strs[i]` consists of lowercase English letters.

## Solution

```ruby
# @param {String[]} strs
# @return {String[][]}
def group_anagrams(strs)
  hm = Hash.new {|hash, key| hash[key] = []}

  strs.each do |s|
    sorted_str = s.chars.sort.join
    hm[sorted_str] << s
  end

  hm.values
end
```