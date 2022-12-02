### Advent of Code 2022

This is my first time writing APL code.

[Problem 1](https://adventofcode.com/2022/day/1)

``` apl
⍝ 1 Part 1
data←⎕NGET'/input1.txt' 1

⌈/+/¨{⍎⍤1⊢↑⍵}¨{(0≠≢¨⍵)⊆⍵}data

⍝ 1 Part 2
s ← +/¨{⍎⍤1⊢↑⍵}¨{(0≠≢¨⍵)⊆⍵}data ⋄ +/s[(3↑⍒s)]
```

