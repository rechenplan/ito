# 1. P spaces

## Definition 1.1: P space

Let A be a set and <= be a relation on A. We say (A, <=) is a P space iff for all x, y, z in A

    (A0) x <= x
    (A1) x <= y and y <= z implies x <= z

## Definition 1.2: upper bound

Let X be a subset of A and b in A. We say b is a *upper bound* of X iff x <= b for all x in X.

## Definition 1.3: join

Let X be a subset of A and j in A. We say j is a *join* of X and we write join(X, j) iff j is an upper bound of X 
and j <= b for b in A when b is an upper bound of X.

## Definition 1.4: lower bound

Let X be a subset of A and b in A. We say b is a *lower bound* of X iff b <= x for all x in X.

## Definition 1.5: meet

Let X be a subset of A and m in A. We say m is a *meet* of X and we write meet(X, m) iff m is a lower bound of X
and b <= m for b in A when b is a lower bound of X.

## Definition 1.7

Let A be a P space. Let a, b in A. We say a and b are join equivalent and write a ~ b iff for all subsets Y of A 
we have join(X, a) = join(Y, b).

## Lemma 1.8

Suppose (A, <=) is a P space. For all a in A, join({ a }, a).

Proof:

Take a in A. By (A0) we have a <= a, which implies a is an upper bound of { a } by (1.2). Let x be
an upper bound of { a }. Then a <= x by (1.2) implies a is a join of { a } by (1.3). Thus we write
join({ a }, a).

QED

## Lemma 1.9

Suppose (A, <=) is a P space. For all a in A, meet({ a }, a).

Proof:

Take a in A. By (A0) we have a <= a, which implies a is a lower bound of { a } by (1.4). Let x be
a lower bound of { a }. Then x <= a by (1.4) implies a is a meet of { a } by (1.5). Thus we write
meet({ a }, a).

# 2. Some thoughts on P spaces

## Theorem 2.1

Let A be a P space. If there exists a subset X of A and a, b in A s.t. join(X, a) and join(X, b) then a ~ b.

Proof:

Suppose there exists a subset X of A and a, b in A s.t. join(X, a) and join(X, b).

If join(X, b), then b is an upper bound of X. This implies a <= b (*) because join(X, a).
If join(X, a), then a is an upper bound of X. This implies b <= a (**) because join(X, b).

Let Y be any subset of A. Either join(Y, a) or not join(Y, a).

If join(Y, a), then we have y <= a for all y in Y. We also have a <= b by (*), so by (A1) we have y <= b for all 
y in Y. Therefore b is an upper bound of Y. Moreover, for all y' in A s.t. y' is an upper bound of Y, we have 
a <= y'. We also have b <= a by (**), so by (A1) we have b <= y'. Thus, join(Y, b).

If not join(Y, a), then either (I) there exists y in Y s.t. not y <= a or (II) there exists y' in A, an upper
bound of Y, s.t. not a <= y'. Suppose join(Y, b). If (I) then there exists y in Y s.t. not y <= a but y <= b by
join(Y, b). However, by (**) we have b <= a, so y <= a by (A1) # Thus, not join(Y, b). If (II) then for all 
upper bounds of Y, such as y', we have b <= y'. But by (*) we have a <= b, which implies a <= y' by (A1) #
Thus, not join(Y, b).

Therefore join(Y, a) => join(Y, b). The converse similarly. Therefore join(Y, a) = join(Y, b), which implies
a ~ b by definition.

QED

## Corollary 2.2

Let A be a P space. For all a, b in A, a ~ b iff and join({ a }, b)

Proof:

If a ~ b, then for all subsets Y of A we have join(Y, a) = join(Y, b). We know join({ a }, a) by 
(1.8), so join({ a }, b).

Suppose join({ a }, b). Let X = { a }. Then we have join(X, a) and join(X, b) by (1.8). If join(X, a) and join(X, b)
then for all subsets Y of A we have join(Y, a) = join(Y, b) by (2.1). This is to say a ~ b.

QED

## Lemma 2.3

Let A be a P space. For all a, b, c in A

1. a ~ a
2. a ~ b implies b ~ a
3. a ~ b and b ~ c implies a ~ c

Proof:

Let X be an arbitrary subset of A.

(1) join(X, a) = join(X, a) implies x ~ x.

(2) a ~ b implies join(X, a) = join(X, b) implies join(X, b) = join(X, a) implies b ~ a.

(3) b ~ c implies join(X, b) = join(X, c). a ~ b implies join(X, a) = join(X, b). Thus, join(X, a) = join(X, c)
which implies a ~ c.

# 3. T spaces

## Definition 3.1: T space

Let (A, <=) be a P space. We say (A, <=) is a T space iff

    (A2) Every subset of A has a join
    (A3) Every finite subset of A has a meet
