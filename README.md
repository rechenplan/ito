# 1. P spaces

## Definition 1.1: P space

Let A be a set and <= be a relation on A. We say (A, <=) is a P space iff for all x, y, z in A

    (A0) x <= x
    (A1) x <= y and y <= z implies x <= z

## Definition 1.2: upper bound

Let X be a subset of A and b in A. We say b is a *upper bound* of X iff x <= b for all x in X.

## Definition 1.3: join

Let J:P(A) -> P(A) where P(A) denotes the power set of A.

Let X be a subset of A and j in A. We say j is a *join* of X and we write j in J(X) iff j is an upper bound of X 
and j <= b for b in A when b is an upper bound of X.

## Definition 1.4: lower bound

Let X be a subset of A and b in A. We say b is a *lower bound* of X iff b <= x for all x in X.

## Definition 1.5: meet

Let M:P(A) -> P(A) where P(A) denotes the power set of A.

Let X be a subset of A and m in A. We say m is a *meet* of X and we write m in M(X) iff m is a lower bound of X
and b <= m for b in A when b is a lower bound of X.

## Definition 1.7

Let A be a P space. Let a, b in A. We say a and b are join equivalent and write a ~ b iff for all subsets X of A 
we have a in J(X) iff b in J(X).

## Lemma 1.8

Suppose (A, <=) is a P space. For all a in A, a in J({ a }).

Proof:

Take a in A. By (A0) we have a <= a, which implies a is an upper bound of { a } by (1.2). Let x be
an upper bound of { a }. Then a <= x by (1.2) implies a in J({ a }) by (1.3).

QED

## Lemma 1.9

Suppose (A, <=) is a P space. For all a in A, a in M({ a }).

Proof:

Take a in A. By (A0) we have a <= a, which implies a is a lower bound of { a } by (1.4). Let x be
a lower bound of { a }. Then x <= a by (1.4) implies a in M({ a }) by (1.5).

# 2. Some thoughts on P spaces

## Theorem 2.1

Let A be a P space. Take a, b in A. If there exists a subset X of A s.t. a, b in J(X) then a ~ b.

Proof:

Take any a, b in A. Suppose there exists a subset X of A s.t. a, b in J(X).

If b in J(X), then b is an upper bound of X. This implies a <= b (*) because a in J(X).
If a in J(X), then a is an upper bound of X. This implies b <= a (**) because b in J(X).

Let Y be any subset of A. Either a in J(Y) or not a in J(Y).

If a in J(Y), then we have y <= a for all y in Y. We also have a <= b by (*), so by (A1) we have y <= b for all 
y in Y. Therefore b is an upper bound of Y. Moreover, for all y' in A s.t. y' is an upper bound of Y, we have 
a <= y'. We also have b <= a by (**), so by (A1) we have b <= y'. Thus, b in J(Y).

If not a in J(Y), then either (I) there exists y in Y s.t. not y <= a or (II) there exists y' in A, an upper
bound of Y, s.t. not a <= y'. Suppose b in J(Y). If (I) then there exists y in Y s.t. not y <= a but y <= b by
b in J(Y). However, by (**) we have b <= a, so y <= a by (A1) # Thus, not b in J(Y). If (II) then for all 
upper bounds of Y, such as y', we have b <= y'. But by (*) we have a <= b, which implies a <= y' by (A1) #
Thus, not b in J(Y).

Therefore a in J(Y) => b in J(Y). The converse similarly. Therefore a in J(Y) iff b in J(Y) which implies
a ~ b by definition.

QED

## Corollary 2.2

Let A be a P space. For all a, b in A, a ~ b iff and b in J({ a })

Proof:

If a ~ b, then for all subsets Y of A we have a in J(Y) iff b in J(Y). We know a in J({ a }) by 
(1.8), so b in J({ a }).

Suppose b in J({ a }). Let X = { a }. Then we have a in J(X) and b in J(X) by (1.8). If a, b in J(X)
then a ~ b (2.1).

QED

## Lemma 2.3

Let A be a P space. For all a, b, c in A

1. a ~ a
2. a ~ b implies b ~ a
3. a ~ b and b ~ c implies a ~ c

Proof:

Let X be an arbitrary subset of A.

(1) a in J(X) iff a in J(X) implies x ~ x.

(2) a ~ b implies a in J(X) iff b in J(X) implies b in J(X) iff a in J(X) implies b ~ a.

(3) b ~ c implies b in J(X) iff c in J(X). a ~ b implies a in J(X) iff J(X).
Thus, a in J(X) iff c in J(X) which implies a ~ c.

# 3. T spaces

## Definition 3.1: T space

Let (A, <=) be a P space. We say (A, <=) is a T space iff

    (A2) Every subset of A has a join
    (A3) Every finite subset of A has a meet
