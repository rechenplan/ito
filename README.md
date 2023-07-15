# 1. P spaces

## Definition 1.1: P space

Let A be a set and <= be a relation on A. We say (A, <=) is a P space iff for all x, y, z in A

    (A0) x <= x
    (A1) x <= y and y <= z implies x <= z

## Definition 1.2: upper bound

Let X be a subset of A and b in A. We say b is a *upper bound* of X iff x <= b for all x in X.

## Definition 1.3: join

Let X be a subset of A and j in A. We say j is a *join* of X and we write j in join(X) iff j is an upper bound of X 
and j <= b for b in A when b is an upper bound of X.

## Definition 1.4: lower bound

Let X be a subset of A and b in A. We say b is a *lower bound* of X iff b <= x for all x in X.

## Definition 1.5: meet

Let X be a subset of A and m in A. We say m is a *meet* of X and we write m in meet(X) iff m is a lower bound of X
and b <= m for b in A when b is a lower bound of X.

## Definition 1.7

Let A be a P space. Let a, b in A. We say a and b are join equivalent and write a ~ b iff for all subsets X of A 
we have a in join(X) iff b in join(X).

## Lemma 1.8

Suppose (A, <=) is a P space. For all a in A, a in join({ a }).

Proof:

Take a in A. By (A0) we have a <= a, which implies a is an upper bound of { a } by (1.2). Let x be
an upper bound of { a }. Then a <= x by (1.2) implies a in join({ a }) by (1.3).

QED

## Lemma 1.9

Suppose (A, <=) is a P space. For all a in A, a in meet({ a }).

Proof:

Take a in A. By (A0) we have a <= a, which implies a is a lower bound of { a } by (1.4). Let x be
a lower bound of { a }. Then x <= a by (1.4) implies a in meet({ a }) by (1.5).

# 2. Some thoughts on P spaces

## Theorem 2.1

Let A be a P space. Take a, b in A. If there exists a subset X of A s.t. a, b in join(X) then a ~ b.

Proof:

Take any a, b in A. Suppose there exists a subset X of A s.t. a, b in join(X).

If b in join(X), then b is an upper bound of X. This implies a <= b (*) because a in join(X).
If a in join(X), then a is an upper bound of X. This implies b <= a (**) because b in join(X).

Let Y be any subset of A. Either a in join(Y) or not a in join(Y).

If a in join(Y), then we have y <= a for all y in Y. We also have a <= b by (*), so by (A1) we have y <= b for all 
y in Y. Therefore b is an upper bound of Y. Moreover, for all y' in A s.t. y' is an upper bound of Y, we have 
a <= y'. We also have b <= a by (**), so by (A1) we have b <= y'. Thus, b in join(Y).

If not a in join(Y), then either (I) there exists y in Y s.t. not y <= a or (II) there exists y' in A, an upper
bound of Y, s.t. not a <= y'. Suppose b in join(Y). If (I) then there exists y in Y s.t. not y <= a but y <= b by
b in join(Y). However, by (**) we have b <= a, so y <= a by (A1) # Thus, not b in join(Y). If (II) then for all 
upper bounds of Y, such as y', we have b <= y'. But by (*) we have a <= b, which implies a <= y' by (A1) #
Thus, not b in join(Y).

Therefore a in join(Y) => b in join(Y). The converse similarly. Therefore a in join(Y) iff b in join(Y) which implies
a ~ b by definition.

QED

## Corollary 2.2

Let A be a P space. For all a, b in A, a ~ b iff and b in join({ a })

Proof:

If a ~ b, then for all subsets Y of A we have a in join(Y) iff b in join(Y). We know a in join({ a }) by 
(1.8), so b in join({ a }).

Suppose b in join({ a }). Let X = { a }. Then we have a in join(X) and b in join(X) by (1.8). If a, b in join(X)
then a ~ b (2.1).

QED

## Lemma 2.3

Let A be a P space. For all a, b, c in A

1. a ~ a
2. a ~ b implies b ~ a
3. a ~ b and b ~ c implies a ~ c

Proof:

Let X be an arbitrary subset of A.

(1) a in join(X) iff a in join(X) implies x ~ x.

(2) a ~ b implies a in join(X) iff b in join(X, b) implies b in join(X) iff a in join(X) implies b ~ a.

(3) b ~ c implies b in join(X) iff c in join(X). a ~ b implies a in join(X) iff join(X, b).
Thus, a in join(X) iff c in join(X) which implies a ~ c.

# 3. T spaces

## Definition 3.1: T space

Let (A, <=) be a P space. We say (A, <=) is a T space iff

    (A2) Every subset of A has a join
    (A3) Every finite subset of A has a meet
