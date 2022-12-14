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

[Problem 2](https://adventofcode.com/2022/day/2)

``` apl
⍝ 2 Part 1
data←⊃⎕NGET'input2.txt'1

s← {⊂[1]  ((↑⍵)∊'AX') + (2×(↑⍵)∊'BY') + (3×(↑⍵)∊'CZ')}data
+/↑ s[3] + (3 × (s[1] = s[3])) + (6 × ((3|(s[1] +1)) = 3|s[3]))

⍝ 2 Part 2
+/↑ (((((s[1] - 1) × (s[1] ≠ 1)) + (s[1] + 2)  × (s[1] = 1) ) × (s[3] = 1)) + ((s[1] + 3) × (s[3] = 2)) + (7 + 3|s[1]) × (s[3] = 3))
```

[Problem 3](https://adventofcode.com/2022/day/3)

``` apl
⍝ 3 Part 1
data←⊃⎕NGET'input3.txt'1

+/{vals ← ((26 + ⍳26), ⍳26)[(⎕A, (¯1∘⎕C ⎕A))⍸⍵]  ⋄  l ← 0.5×⍴⍵ ⋄ ∪(((l⍴1), l⍴0)/vals)∩(((l⍴0),(l⍴1))/vals)  }¨data

⍝ 3 Part 2

+/{⊃∪↑3∩/⍵}¨(3/⍳(÷3)×≢data)⊆{((26 + ⍳26), ⍳26)[(⎕A, (¯1∘⎕C ⎕A))⍸⍵]}¨data
```

[Problem 4](https://adventofcode.com/2022/day/4)

``` apl
⍝ 4 Part 1
data←⊃⎕NGET'input4.txt'1

+/ {0≥×/×+/(2 4⍴1 0 ¯1 0   0 1 0 ¯1) × 2 4⍴⍎¨'-,'(~⍤∊⍨⊆⊢)⍵}¨data

⍝ 4 Part 2

+/{m ← ⍎¨'-,'(~⍤∊⍨⊆⊢)⍵ ⋄ 0≤(m[4]⌊m[2])-(m[3]⌈m[1])}¨data
```

[Problem 5](https://adventofcode.com/2022/day/5)

``` apl
⍝ 5 Part 1
data←⊃⎕NGET'input5.txt'1

stack ← ↑8↑data
columns ← ~∘' '¨(↓(⍉stack))[2 + 4 × ¯1 + ⍳9]
instructions ← 10↓data
{howmany ← ⍎⍵[6 7] ⋄ from ← ⍎⍵[13 14] ⋄ to ← ⍎⍵[(≢⍵)] ⋄ columns[to] ← ↓(⌽howmany↑↑columns[from]), ↑columns[to] ⋄columns[from] ← ↓howmany↓↑columns[from]}¨instructions
1↑¨ columns

⍝ 5 Part 2

columns ← ~∘' '¨(↓(⍉stack))[2 + 4 × ¯1 + ⍳9]
{howmany ← ⍎⍵[6 7] ⋄ from ← ⍎⍵[13 14] ⋄ to ← ⍎⍵[(≢⍵)] ⋄ columns[to] ← ↓(howmany↑↑columns[from]), ↑columns[to] ⋄columns[from] ← ↓howmany↓↑columns[from]}¨instructions
1↑¨ columns
```

[Problem 6](https://adventofcode.com/2022/day/6)

``` apl
⍝ 6 Part 1
data←⊃⎕NGET'input6.txt'1

3 + ⊃⍸4=(≢∪)¨4,/↑data[1]

⍝ 6 Part 2

13 + ⊃⍸14=(≢∪)¨14,/↑data[1]
```


[Problem 7](https://adventofcode.com/2022/day/7)

Lots of parsing. Beyond my APL skills.
