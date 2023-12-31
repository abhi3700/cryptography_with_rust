# Maths for Cryptography

| Arithmetic Operations | Terms |
| --------------------- | ----- |
| `+ -`                 | Group |
| `+ - *`               | Ring  |
| `+ - * /`             | Field |

🔝 This also means that:

- every **field** is a **ring**
- every **ring** is a abelian group
- every abelian group is a **group**.

Now, let's summarize the difference between Linear & Abstract Algebra:

| Linear Algebra | Abstract Algebra        |
| -------------- | ----------------------- |
| Addition       | Addition                |
| Subtraction    | Additive Inverses       |
| Multiplication | Multiplication          |
| Division       | Multiplicative Inverses |

> NOTE: In case of abstract algebra, even after following this, if the result is not in the range of the modulus, then it is remaindered with the modulus (until it falls within the range).

> **Abstract Algebra** was introduced to understand the abstract objects like in Cryptography where we need to understand the abstract objects like _Elliptic Curves_ and _Finite Fields_. It is a generalization of the algebraic structures like _Groups_, _Rings_ and _Fields_. It is a study of algebraic structures.

## Group

## Ring

## Field

<details>
<summary><b>Details:</b></summary>

Here w.r.t. Cryptography, we will be dealing with _Finite Fields_.

In Finite Field (also a part of Abstract Algebra), arithmetic operations are done with a modulus i.e. `mod p` where `p` is a large prime number in a finite field.

> Whenever, finite field is mentioned, it is assumed that the modulus is a prime number i.e. with modulus is 1. like:
>
> - Additive inverse of `-5` ≡ `5`. Think of it as `-5 + 5 = 0`, following `(a + b) = 0`. Consider `0` as the additive identity (like a mirror 🪞 in real world). Visually, `-5 |0| 5` where, 0 is the axis in between -5 and 5.
> - Multiplicative inverse of `1/5` ≡ `5`. Think of it as `1/5 * 5 = 1`, following `(a * b) = 1`. Consider `1` as the multiplicative identity (like a mirror 🪞 in real world). Visually, `1/5 |1| 5` where 1 is the axis in between 1/5 and 5.

> For simplicity, we will use `mod 7` as the modulus for all the examples below.

**Q**. Why Finite Field?

**A**. Watch this [video](https://www.youtube.com/watch?v=ColSUxhpn6A).

**Q**. Why p should be a prime number in a finite field?

**A**. Because we won't have an integer ℤ determined during multiplicative inverses. For instance, there is no multiplicative inverse of 5 i.e. (`1/5`) with modulus like `100` (which is a non-prime no). Hence, we need to have a prime number as the modulus.

### Addition

```math
3 + 5 = 8 (mod 7) ≡ 1 (mod 7)
```

> NOTE: ≡ is used for equivalence in modular arithmetic to distinguish it from equality meaning "equivalent to".

> Here, we do:
>
> 1. _addition_
> 2. _remainder_

### Subtraction

```math
3 - 5 = 3 + (-5) = -2 (mod 7) ≡ 5 (mod 7)
```

> Here, we do:
>
> 1. _addition_
> 2. _additive inverse_

The inverse taken here is called _additive inverse_. Like `-2 + 7 = 5`.

The modulus is kept on adding to the negative number (however big it is), until it becomes positive. Once it is positive and if by chance doesn't fall into the range of the modulus `{1,...,m-1}`, it is then remaindered with the modulus like `52 % 7 = 3`.

> By the way, there are many kinds of inverses in a field.

### Multiplication

```math
3 * 5 = 15 (mod 7) ≡ 1 (mod 7)
```

> Here, we do:
>
> 1. _multiplication_
> 2. _remainder_

### Division

```math
3 / 5 = 3 * (1/5) ≡ 3 * 3 = 9 (mod 7) ≡ 2 (mod 7)
```

> In order to determine modular multiplicative inverse of 5 (also represented as (1/5) or 5^-1) mod 7, we need to find a number b such that:
>
> `(a * b) % 7 = 1`
>
> `(5 * b) % 7 = 1` => `b = 5`, trying out different values.

> Here, we do:
>
> 1. _multiplicative inverse_
> 2. _multiplication_
> 3. _remainder_

</details>

## References

- [Field Definition (expanded) - Abstract Algebra](https://www.youtube.com/watch?v=KCSZ4QhOw0I)
- [Finite Fields in Cryptography: Why and How](https://www.youtube.com/watch?v=ColSUxhpn6A&t=495s)

## Resources

- [Algebra maths for ZKP by @Pratyush](https://github.com/Pratyush/algebra-intro)
- [Rust lib for Galois Field arithmetic with GF(2^256) i.e. 256-bit prime no.](https://github.com/geky/gf256) [RECOMMENDED]
- [Rust lib for GF(2^8) i.e. 8-bit prime no.](https://github.com/rustyhorde/sss)
