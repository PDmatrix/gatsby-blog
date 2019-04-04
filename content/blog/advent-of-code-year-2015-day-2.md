---
title: Advent of Code. Year 2015. Day 2
date: 2019-03-31T17:11:44.827Z
description: Advent of Code. Year 2015. Day 2
tags:
  - aoc-2015
---
## --- Day 2: I Was Told There Would Be No Math ---

In this challenge we have to help elves by calculating the required wrapping paper for each gift. Fortunately, they gave us a formula, which makes things a little easier. The elves also need a little extra paper for each present: the area of the smallest side.

### Part 1

In part one we have to find how many total square feet of wrapping paper should they order. 

```csharp
public string Part1(IEnumerable<string> input)
{
  var result = 0;
  foreach (var dimension in input)
  {
    var dims = dimension.Split('x').Select(int.Parse).ToList();
    int l = dims[0],
        w = dims[1],
        h = dims[2];
    var smallestSide = Math.Min(Math.Min(l * w, w * h), h * l); //highlight-line
    result += smallestSide + 2 * l * w + 2 * w * h + 2 * h * l; //highlight-line
  }
  return result.ToString();
}
```

### Part 2

second part description

```csharp
solution
```

---
Links:
* [Puzzle](https://adventofcode.com/2015/day/2)
* [Solution](https://github.com/PDmatrix/advent-of-code/tree/master/CSharp/Solutions/2015/2)
