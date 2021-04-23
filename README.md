## Question 1

### a. <br/>
Useful attribute closures:
[B<sup>+</sup>] → B <br/>
[BA<sup>+</sup>] → A,B,C,D <br/>
[BC<sup>+</sup>] → A,B,C,D <br/>
[BD<sup>+</sup>] → A,B,C,D <br/>

∴ Candidate keys = `BA, BC, BD`

### b. <br/>
BNCF violations: `C → D and D → A`

Decomposing C → D:
```
(ABCD)
  |    \
C → D   |
  |     |
(CD)  (ABC)
        |    \
      C → A   |
        |     |
       (CA)  (AC)
```

∴ Collection of relations: R1(CD), R2(AC), and R3(BC)

Decomposing D → A:

```
(ABCD)
  |    \
D → A   |
  |     |
(AD)  (BCD)
        |    \
      C → D   |
        |     |
       (CD)  (BC)
```

∴ Collection of relations: R1(AD), R2(CD), and R3(BC)

### c.<br/>
Decomposing  `C → D` does not preserve `D → A` and `AB → C`
Decomposing `D → A` does not preserve `AB → C`

## Question 2


## Question 3
RA symbols used: π, σ, ⋈, ∪
TRC symbols used: ∃, ∈, ∧

a. <br/>
π<sub>bcolor</sub>[(σ<sub>sname='albert'</sub>(sailors)) ⋈ reserves ⋈ boat]

b. <br/>
π<sub>sid</sub>(σ<sub>rating≥8(sailors)</sub>) ∪ π<sub>sid</sub>[σ<sub>bid=103</sub>(reserves)]

c. <br/>
{S | ∃S1 ∈ Sailors(S1.rating < 3 ∧ S.sname = S1.sname ∧ S.age = S1.age)}

d. <br/>
{<B> | <S,B,D> ∈ Reserves ∧ D='2019-04-28'}

e. <br/>
{<C> | <B,N> ∈ Boat ∧ ∃<S,B,D> ∈ Reserves ∧ ∃<S,'Lubber', R,A> ∈ Sailors }


## Question 4
1 - B <br/>
2 - D <br/>
3 - C <br/>
4 - A <br/>
5 - E <br/>

## Question 5

### a
```
				[65]
			[24|50]	[75|88]
[2|10] [24|45|48] [50|56] [65|72] [88|93]
```

### b.
```
		[48|72]
[2|10|45] [48|56] [72|87|88]
```

## Question 6

### a. <br/>
Brand
|Opel|Peugeot|BMW|
|---|---|---|
|1|0|0|
|1|0|0|
|0|1|0|
|0|0|1|

Color
|Grey|Red|Black|
|---|---|---|
|1|0|0|
|0|1|0|
|0|0|1|
|0|0|1|

### b. <br/>
#### i  <br/>
First, we need to analyse the bitmap index for Black: [0 0 1 1]. <br/>
Then, the answer is obtained by accessing tuples with 1-entries: 3rd and 4th.

#### ii  <br/>
First, we intersect the bitmap for Opel with the bitmap index for Red by taking the logical
AND of the bitmaps, resulting in the bitmap: [0 1 0 0]. <br/>
Then, we check if the condition Risk=medium is satisfied for all tuples with 1-entries. In this case, only the second tuple is accessed. The final result 1 is returned.


## Question 7

### a
|000|001|010|011|100|101|110|111|
|---|---|---|---|---|---|---|---|
|4, 12, 16, 20 (overflow)|13|2, 6|/|/|/|/|/|

### b
No because there are too many search key values that have to go in the 000 bucket, despite having previously split the 0 and 00 buckets and rehashed their contents for the remaining values. It is better to use search key values that aren't multiples of 4.
