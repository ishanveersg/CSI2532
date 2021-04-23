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

a. 
`π<sub>bcolor</sub>[(σ<sub>sname='albert'</sub>(sailors)) ⋈ reserves ⋈ boat]`

b. 
`π<sub>sid</sub>(σ<sub>rating≥8(sailors)</sub>) ∪ π<sub>sid</sub>[σ<sub>bid=103</sub>(reserves)]`

c. 
`{S | ∃S1 ∈ Sailors(S1.rating < 3 ∧ S.sname = S1.sname ∧ S.age = S1.age)}`

d. 
`{<B> | <S,B,D> ∈ Reserves ∧ D='2019-04-28'}`

e. 
`{<C> | <B,N> ∈ Boat ∧ ∃<S,B,D> ∈ Reserves ∧ ∃<S,'Lubber', R,A> ∈ Sailors }`


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
We analyse the bitmap for Black: [0 0 1 1]. We take the tuples in the relation where the entries are 1. Thus, the 3rd and 4th tuples are taken. The final result is the corresponding tuples. 

#### ii  <br/>
We analyse the result of (bitmap for Opel) AND (bitmap for Red): [0 1 0 0]. We take the tuples in the relation where the entries are 1. We then check the tuples where Risk=medium. The tuples that satisfy this condition are counted. Thus, only the 2nd tuples is counted. The final result is 1. 


## Question 7

### a
|000|001|010|011|100|101|110|111|
|---|---|---|---|---|---|---|---|
|4, 12, 16, 20 (overflow)|13|2, 6|/|/|/|/|/|

### b
No. There are too many search key values that have to go in the 000 bucket, despite having previously split the 0 and 00 buckets and rehashed their contents for the remaining values. It'd be better to use search key values that aren't multiples of 4.
