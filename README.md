## Question 1

a.
Useful attribute closures:
[B<sup>+</sup>] → B
[BA<sup>+</sup>] → A,B,C,D
[BC<sup>+</sup>] → A,B,C,D
[BD<sup>+</sup>] → A,B,C,D

∴ Candidate keys = `BA, BC, BD`

b.
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

c.
Decomposing  C → D does not preserve D → A and AB → C
Decomposing D → A does not preserve AB → C

## Question 2


## Question 3
RA symbols used: π, σ, ⋈, ∪
TRC symbols used: ∃, ∈, ∧

a. π<sub>bcolor</sub>[(σ<sub>sname='albert'</sub>(sailors)) ⋈ reserves ⋈ boat]

b. π<sub>sid</sub>(σ<sub>rating≥8(sailors)</sub>) ∪ π<sub>sid</sub>[σ<sub>bid=103</sub>(reserves)]

c. {S | ∃S1 ∈ Sailors(S1.rating < 3 ∧ S.sname = S1.sname ∧ S.age = S1.age)}

d. {<B> | <S,B,D> ∈ Reserves ∧ D='2019-04-28'}

e. {<C> | <B,N> ∈ Boat ∧ ∃<S,B,D> ∈ Reserves ∧ ∃<S,'Lubber', R,A> ∈ Sailors }


## Question 4

## Question 5

## Question 6

## Question 7

