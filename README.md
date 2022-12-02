### Advent of Code 2022

This is my first time writing APL code.

[Problem 1](https://adventofcode.com/2022/day/1)

``` apl
⍝ 1 Part 1
data←⎕NGET'input1.txt'1

⌈/+/¨{⍎⍤1⊢↑⍵}¨{(0≠≢¨⍵)⊆⍵}data

⍝ 1 Part 2
s ← +/¨{⍎⍤1⊢↑⍵}¨{(0≠≢¨⍵)⊆⍵}data ⋄ +/s[(3↑⍒s)]
```

[Problem 1](https://adventofcode.com/2022/day/2)

``` apl
⍝ 2 Part 1
data←⊃⎕NGET'input2.txt'1

s← {⊂[1]  ((↑⍵)∊'AX') + (2×(↑⍵)∊'BY') + (3×(↑⍵)∊'CZ')}data
+/↑ s[3] + (3 × (s[1] = s[3])) + (6 × ((3|(s[1] +1)) = 3|s[3]))

⍝ 2 Part 2
+/↑ (((((s[1] - 1) × (s[1] ≠ 1)) + (s[1] + 2)  × (s[1] = 1) ) × (s[3] = 1)) + ((s[1] + 3) × (s[3] = 2)) + (7 + 3|s[1]) × (s[3] = 3))
```

