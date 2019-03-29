---
title: 'Advent of Code - Year 2015 - Day 01, Day 02'
date: 2019-03-29T16:35:12.099Z
description: 'Solution to Advent of Code Year 2015 - Day 01, Day 02'
---
_This is my first blog post in a fascinating series of Advent of Code puzzles, where I sincerely try to properly explain workable solutions. All solutions will be solved using language C#._

---

## --- Day 1: Not Quite Lisp ---

In this puzzle we got Santa trying to deliver presents in a large apartment building, but he can't find the right floor. He starts on the ground floor (floor 0) and then follows the instructions one character at a time. Instructions looks like this `()(((()))(()()()((((()(((())(()(()((((((()`, where opening parenthesis, `(`, means he should go up one floor, and a closing parenthesis, `)`, means he should go down one floor.

### Part 1

Our goal for the first part was to calculate what floor do the instructions take Santa. My solution for this part was pretty easy, I take every instruction and depending on the value I either sum result by 1 or -1.
```csharp
public string Part1(IEnumerable<string> input)
{
    var directions = input.First();
    return directions.Sum(r => r == '(' ? 1 : -1).ToString();
}
```
