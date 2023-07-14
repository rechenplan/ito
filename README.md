# 1. Clementine spaces

## Definition 1.1: transitive space

Suppose we have a set A and a transitive binary relation -> on A. That is, for all x, y, z in A

    (A1) x -> y and y -> z implies x -> z

we call (A, ->) a *transitive space*.

## Definition 1.2: upper bound

Let X be a subset of A, x' in A. We say x' is a *upper bound* or UB of X iff x -> x' for all x in X.

## Definition 1.3: join

Let X be a subset of A, y in A. We say y is a *join* of X and we write X(y) iff y is a UB of X 
and y -> x' for all x' in A s.t. x' is a UB of X.

## Definition 1.4: Clementine space

Suppose (A, ->) is a transitive space. If

    (A2) For all a in A, there exists a subset X of A s.t. X(a)

then we call (A, ->) a *Clementine space*.

# 2. Some theorems on Clementine spaces

## Theorem 2.1

Let A be a Clementine space. Let X and Y be subsets of A. For all a, b in A, if X(a) and X(b) then Y(a) = Y(b).
Proof:

Suppose both X(a) and X(b).

If X(b), then b is an UB of X. This implies a -> b (*) because X(a).
If X(a), then a is an UB of X. This implies b -> a (**) because X(b).

Either Y(a) or not Y(a).

If Y(a), then we have y -> a for all y in Y. We also have a -> b by (*), so by (A1) we have y -> b for all 
y in Y. Therefore b is a UB of Y. Moreover, for all y' in A s.t. y' is a UB of Y, we have a -> y'. We also
have b -> a by (**), so by (A1) we have b -> y'. Thus, Y(b).

If not Y(a), then either (I) there exists y in Y s.t. not y -> a or (II) there exists y' in A, a UB
of Y, s.t. not a -> y'. Suppose Y(b). If (I) then there exists y in Y s.t. not y -> a but y -> b by Y(b). 
However, by (**) we have b -> a, so y -> a by (A1) # Thus, not Y(b). If (II) then for all UBs of Y,
such as y', we have b -> y'. But by (*) we have a -> b, which implies a -> y' by (A1) # Thus, not Y(b).

Therefore Y(a) => Y(b). The converse similarly. Therefore Y(a) = Y(b).

QED.

## Definition 2.2

Let A be a Clementine space. Let X be a subset of A. For all a, b in A, we write a ~X b iff X(a) = X(b).

## Definition 2.3

We say a and b are join equivalent and write a ~ b iff there exists a subset X of A s.t. a ~X b and X(a).

## Corollary 2.4

Let A be a Clementine space. For all a, b in A, a ~ b iff for all subsets Y of A we have a ~Y b.

Proof:

If a ~ b, then a ~X b and X(a). If a ~X b and X(a), then X(a) and X(b). If X(a) and X(b) then for all 
subsets Y of A we have Y(a) = Y(b) by (2.1). Thus, for all subsets Y of A we have a ~Y b.

Suppose for all subsets Y of A, we have a ~Y b. By (A2) there exists a subset X of A s.t. X(a).
Thus, a ~X b (by supposition) and X(a). Therefore a ~ b.

QED.

## Lemma 2.5

Let A be a Clementine space. For all a, b, c in A

1. a ~ a
2. a ~ b implies b ~ a
3. a ~ b and b ~ c implies a ~ c

Proof:

(1) By (A2) there exists X s.t. X(a). Clearly X(a) = X(a), so a ~X a and X(a). Therefore a ~ a.

(2) a ~ b implies a ~X b and X(a) for some subset X of A. This means X(a) = X(b) and X(a), which implies
X(b) = X(a) and X(b). Thus, b ~X a and X(b). Therefore b ~ a.

(3) b ~ c implies b ~Y c and Y(b) for some subset Y of A. Furthermore, a ~ b implies b ~ a implies b ~Y a by (1.3). 
Since b ~Y a and Y(b), we have Y(a). b ~ c also implies c ~ b, so c ~Y b and Y(c). So, Y(a) = Y(c). This is to say
a ~Y c and Y(a), which is to say a ~ c.

# 3. Bobby spaces

## Definition 3.1: Bobby space

Suppose (A, ->) is a Clementine space. Let B = A / ~. Take X, Y in B. We say X => Y iff there exists x in X
and y in Y s.t. x -> y. We call (B, =>) a *Bobby space*.

