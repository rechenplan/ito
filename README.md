# 1. P spaces

## Definition 1.1: P space

Suppose we have a set A and a preorder -> on A. That is, for all x, y, z in A

    (A0) x -> x
    (A1) x -> y and y -> z implies x -> z

we call (A, ->) a *preorder space* or P space.

## Definition 1.2: upper bound

Let X be a subset of A, x' in A. We say x' is a *upper bound* or UB of X iff x -> x' for all x in X.

## Definition 1.3: join

Let X be a subset of A, y in A. We say y is a *join* of X and we write X(y) iff y is a UB of X and y -> x' for all 
x' in A s.t. x' is a UB of X.

## Lemma 1.4

Suppose (A, ->) is a P space. For all a in A, there exists a subset X of A s.t. X(a).

Proof:

Take a in A. Let X = { a }. By (A0) we have a -> a, which implies a is an upper bound of X by (1.2). Let x be
an upper bound of X. Then a -> x by (1.4) implies a is a join of X by (1.3). Thus we write X(a).

QED

# 2. Some thoughts on P spaces

## Theorem 2.1

Let A be a P space. If there exists a subset X of A and a, b in A s.t. X(a) and X(b) then 
for all subsets Y of A we have Y(a) = Y(b).

Proof:

Suppose there exists a subset X of A and a, b in A s.t. X(a) and X(b).

If X(b), then b is an UB of X. This implies a -> b (*) because X(a).
If X(a), then a is an UB of X. This implies b -> a (**) because X(b).

Let Y be any subset of A. Either Y(a) or not Y(a).

If Y(a), then we have y -> a for all y in Y. We also have a -> b by (*), so by (A1) we have y -> b for all 
y in Y. Therefore b is a UB of Y. Moreover, for all y' in A s.t. y' is a UB of Y, we have a -> y'. We also
have b -> a by (**), so by (A1) we have b -> y'. Thus, Y(b).

If not Y(a), then either (I) there exists y in Y s.t. not y -> a or (II) there exists y' in A, a UB
of Y, s.t. not a -> y'. Suppose Y(b). If (I) then there exists y in Y s.t. not y -> a but y -> b by Y(b). 
However, by (**) we have b -> a, so y -> a by (A1) # Thus, not Y(b). If (II) then for all UBs of Y,
such as y', we have b -> y'. But by (*) we have a -> b, which implies a -> y' by (A1) # Thus, not Y(b).

Therefore Y(a) => Y(b). The converse similarly. Therefore Y(a) = Y(b).

QED

## Definition 2.2

Let A be a P space. Let X be a subset of A. For all a, b in A, we write a ~X b iff X(a) = X(b).

## Definition 2.3

Let A be a P space. Let a, b in A. We say a and b are join equivalent and write a ~ b iff there exists a subset 
X of A s.t. a ~X b and X(a).

## Corollary 2.4

Let A be a P space. For all a, b in A, a ~ b iff for all subsets Y of A we have a ~Y b.

Proof:

If a ~ b, then a ~X b and X(a). If a ~X b and X(a), then X(a) and X(b). If X(a) and X(b) then for all 
subsets Y of A we have Y(a) = Y(b) by (2.1). Thus, for all subsets Y of A we have a ~Y b.

Suppose for all subsets Y of A, we have a ~Y b. By (1.4) there exists a subset X of A s.t. X(a).
Thus, a ~X b (by supposition) and X(a). Therefore a ~ b.

QED

## Lemma 2.5

Let A be a P space. For all a, b, c in A

1. a ~ a
2. a ~ b implies b ~ a
3. a ~ b and b ~ c implies a ~ c

Proof:

(1) By (1.4) there exists X s.t. X(a). Clearly X(a) = X(a), so a ~X a and X(a). Therefore a ~ a.

(2) a ~ b implies a ~X b and X(a) for some subset X of A. This means X(a) = X(b) and X(a), which implies
X(b) = X(a) and X(b). Thus, b ~X a and X(b). Therefore b ~ a.

(3) b ~ c implies b ~Y c and Y(b) for some subset Y of A. Furthermore, a ~ b implies b ~ a implies b ~Y a by (1.3). 
Since b ~Y a and Y(b), we have Y(a). b ~ c also implies c ~ b, so c ~Y b and Y(c). So, Y(a) = Y(c). This is to say
a ~Y c and Y(a), which is to say a ~ c.

# 3. J spaces

## Definition 3.1: J spaces

Suppose (A, ->) is a P space. Let B = A / ~. Take X, Y in B. We write X => Y iff there exists y in Y s.t. X(y).
We call (B, =>) the *join space* or J space induced by the P space (A, ->).

## Lemma 3.2

Let (B, =>) be the J space induced by the P space (A, ->). Take X, Y in B. We have X => Y iff for all y in Y
we have X(y).

Proof:

Suppose X => Y. Then there exists y' in Y s.t. X(y'). Take an arbitrary y in Y. By the definition of Y, we have
that y ~ y'. This implies that for all subsets Z of A, we have y ~Z y' by (2.4) => Z(y) = Z(y') by (2.2). For 
Z = X, this implies X(y) = X(y'), which implies X(y).

The converse is trivial.

## Theorem 3.3

Let (B, =>) be the J space induced by the P space (A, ->). Let X in B. If there exists X! in B s.t. X => X!,
then X! is unique.

Proof:

Let X in B. Suppose there exists X! and Y! s.t. X => X! and X => Y!. Let x in X! and y in Y!. If X => X! then 
X(x) by (3.2). If X => Y! then X(y) by (3.2). But this means X(x) = X(y) and X(x). This implies x ~ y, which in turn 
implies X* = Y* by the definition of B. Therefore X! is unique (if it exists).

## Definition 3.4

If X! does not exist, we say X is in *normal form*.
