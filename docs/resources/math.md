---
title: "Matemáticas"
---


# Matemáticas

## Números Primos

- ¿Qué es un número primo?
  - [What's a Prime Number?](https://www.youtube.com/watch?v=9pgA-H77BLc)
  - [Wikipedia - Prime Number](https://en.wikipedia.org/wiki/Prime_number)
- Teorema fundamental de la aritmética: todo natural tiene una única factorización prima
  - [wikipedia - Fundamenetal theorem of arithmetic](https://en.wikipedia.org/wiki/Fundamental_theorem_of_arithmetic)
  - [The Fundamental Theorem of Arithmetic](http://www.oxfordmathcenter.com/drupal7/node/165)
  - [Number Theory - Fundamental Theorem of Arithmetic](https://www.youtube.com/watch?v=7sw6LdAfHgE)
- Tests de Primalidad (cómo saber si un número es primo):
  - [CP-Algorithms: Primality tests](https://cp-algorithms.com/algebra/primality_tests.html)
  - [stackoverflow - Fastest algorithm for primality test](https://stackoverflow.com/questions/2586596/fastest-algorithm-for-primality-test)
  - Miller Rabin:
    - [cp-algorithms: Miller Rabin](https://cp-algorithms.com/algebra/primality_tests.html#toc-tgt-2)
    - <https://www.geeksforgeeks.org/primality-test-set-3-miller-rabin/>
    - deterministic variant: <https://miller-rabin.appspot.com/>
  - [Códigos de ejemplo](https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Mathematics/primality_test.cpp)
- Criba de Eratóstenes (todos los primos hasta N):
  - [wikipedia: Sieve of Eratosthenes](https://en.wikipedia.org/wiki/Sieve_of_Eratosthenes) (hay un GIF muy bueno)
  - (youtube) [Finding Prime numbers - Sieve of Eratosthenes](https://www.youtube.com/watch?v=eKp56OLhoQs)
  - (youtube) [Criba de Eratóstenes [ICPCCL 2016]](https://www.youtube.com/watch?v=J4QCQ0dgeCI)
  - [Código de ejemplo](https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Mathematics/sieve_of_eratosthenes.cpp)
- Criba de Eratóstenes Segmentada (más rápida):
  - <https://github.com/kimwalisch/primesieve/wiki/Segmented-sieve-of-Eratosthenes>
  - (cp-algorithms) [Segmented sieve of eratosthenes](https://cp-algorithms.com/algebra/sieve-of-eratosthenes.html#toc-tgt-6)
  - (geeksforgeeks) [Segmented Sieve (Print Primes in a Range)](https://www.geeksforgeeks.org/segmented-sieve-print-primes-in-a-range/)
- Factorización Prima de Números Enteros:
  - [cp-algorithms: Integer factorization](https://cp-algorithms.com/algebra/factorization.html)
  - [código de ejemplo](https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Mathematics/prime_factorization.cpp)
- Factorización Prima de Factoriales:
  - <http://mathforum.org/library/drmath/view/67291.html>
  - <https://janmr.com/blog/2010/10/prime-factors-of-factorial-numbers/>
  - <https://forthright48.com/prime-factorization-of-factorial/>
  - [código de ejemplo](https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Mathematics/prime_factorization.cpp)

## Aritmética Modular

- ¿De qué se trata Aritmética Modular?
  - [Art of Problem Solving: Modular Arithmetic / Introduction](https://artofproblemsolving.com/wiki/index.php/Modular_arithmetic/Introduction)
  - (wikipedia) [Modular Arithmetic](https://en.wikipedia.org/wiki/Modular_arithmetic)
  - (youtube) [Introduction to Modular arithmetic](https://www.youtube.com/watch?v=9lUSKOjV4d0)
  - (youtube) [High level introduction to modular arithmetic](https://www.youtube.com/watch?v=r0gYad8auYY)
  - (youtube) [Congruence (Modular Arithmetic) & 5 Properties Explained with 7 Problems: Ultimate Shortcuts](https://www.youtube.com/watch?v=B1gD6540uWA)
- (wikipedia) [Identidades en Aritmética Modular](https://en.wikipedia.org/wiki/Modular_arithmetic#Properties)

- Modular Inverse:
  - [cp-algorithms - Modular Inverse](https://cp-algorithms.com/algebra/module-inverse.html)
  - [Youtube - Multiplicative inverses mod n](https://www.youtube.com/watch?v=_bRVA5b4sb4)
- Modular Exponentiation By Squaring:
  - <https://en.wikipedia.org/wiki/Modular_exponentiation#Right-to-left_binary_method>
  - <https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Mathematics/binary_modular_exponentiation.cpp>
- Modular Fibonacci with Exponentiation by Squaring:
  - <http://mathoverflow.net/questions/40816/fibonacci-series-mod-a-number>

## Binary Exponentiation

- (cp-algorithms) [Binary Exponentiation](https://cp-algorithms.com/algebra/binary-exp.html)
- [Código de ejemplo](https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Mathematics/binary_modular_exponentiation.cpp)

## Conteo y Combinatoria modular

- [Muy buen artículo sobre distintos métodos para calcular combinatorias](https://comeoncodeon.wordpress.com/2011/07/31/combination/)
- Modular Binomial Coefficient (Choose(n,k) mod X): [código de ejemplo](https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Mathematics/modular_binomial_coefficient.cpp)
- Modular Multinomial Coefficient: [código de ejemplo](https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Mathematics/modular_multinomial_coefficient.cpp)

## Algoritmo de Euclides

cómo encontrar el GCD entre dos números

- (youtube) [Euclidean Algorithm (Proof)](https://www.youtube.com/watch?v=H_2_nqKAZ5w)
- (youtube) [Number Theory: Euclidean Algorithm - An example](https://www.youtube.com/watch?v=fwuj4yzoX1o)
- (cp-algorithms) [Euclidean algorithm for computing the greatest common divisor](https://cp-algorithms.com/algebra/euclid-algorithm.html)
- (youtube) [(Discrete Math 1) Euclidian Algorithm](https://www.youtube.com/watch?v=cOwyHTiW4KE)
- [Euclidean Algorithm – Greatest Common Divisor](https://forthright48.com/euclidean-algorithm)
- (geeksforgeeks) [std::gcd \| C++ inbuilt function for finding GCD](https://www.geeksforgeeks.org/stdgcd-c-inbuilt-function-finding-gcd/)

LCM (mínimo común múltiplo): <https://cp-algorithms.com/algebra/euclid-algorithm.html> (revisar final de la página)

## Algoritmo de Euclides Extendido (gcdext)

- <https://forthright48.com/extended-euclidean-algorithm/>
- (cp-algorithms) [Extended Euclidean Algorithm](https://cp-algorithms.com/algebra/extended-euclid-algorithm.html)
- (math.stackexchange) [gcdext con números negativos?](https://math.stackexchange.com/questions/37806/extended-euclidean-algorithm-with-negative-numbers)
- (youtube) [Algoritmo de Euclides [ICPCCL 2016]](https://www.youtube.com/watch?v=k47fkSULGr0)
- (youtube) [The Extended Euclidean algorithm](https://www.youtube.com/watch?v=hB34-GSDT3k)
- [código de ejemplo](https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Mathematics/euclidean_algorithm.cpp)

- ### Aplicaciones de Euclides Extendido
  - #### Modular Inverse
    - (cp-algorithms) [modular inverse](https://cp-algorithms.com/algebra/module-inverse.html)
  - #### Linear Diophantine Equations
    - (cp-algorithms) [linear dophantine equation](https://cp-algorithms.com/algebra/linear-diophantine-equation.html)
    - (youtube) [N1--Introduction to Linear Diophantine Equations](https://www.youtube.com/watch?v=TIk3ujphMfk)
    - (youtube) [N2--Solve Basic Linear Diophantine Equation](https://www.youtube.com/watch?v=5DcoG69NyO0)
    - (youtube) [Number Theory: Diophantine Equation: ax+by=gcd(a,b)](https://www.youtube.com/watch?v=FjliV5u2IVw)
    - (PDF) <http://gauss.math.luc.edu/greicius/Math201/Fall2012/Lectures/linear-diophantine.article.pdf>
    - <http://mathonline.wikidot.com/solutions-to-linear-diophantine-equations>
  - #### Linear Congruence Equation
    - (cp-algorithms) [Linear Congruence Equation](https://cp-algorithms.com/algebra/linear_congruence_equation.html)
    - (PDF) <http://gauss.math.luc.edu/greicius/Math201/Fall2012/Lectures/linear-congruences.article.pdf>
  - [Códigos de ejemplos](https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Mathematics/euclidean_algorithm.cpp)

## Chinese Remainder Theorem (CRT)

- (codeforces) [[Tutorial] Chinese Remainder Theorem](https://codeforces.com/blog/entry/61290)
- (youtube) [The Chinese Remainder Theorem made easy](https://www.youtube.com/watch?v=ru7mWZJlRQg)
- (youtube) [Chinese Remainder Theorem](https://www.youtube.com/watch?v=zIFehsBHB8o)
- [Chinese Remainder Theorem Part 1 – Coprime Moduli](https://forthright48.com/chinese-remainder-theorem-part-1-coprime-moduli/)
- [Chinese Remainder Theorem Part 2 – Non Coprime Moduli](https://forthright48.com/chinese-remainder-theorem-part-2-non-coprime-moduli)
- [código de ejemplo](https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Mathematics/chinese_remainder_theorem.cpp)

## Lucas's theorem

- [wikipedia - Lucas's theorem](https://en.m.wikipedia.org/wiki/Lucas%27s_theorem)
- [choose(n,k) mod M using Chinese remainder theorem?](https://math.stackexchange.com/questions/95491/n-choose-k-bmod-m-using-chinese-remainder-theorem)  

## Euler's Theorem & Euler's Totient Function

- [wikipedia - Euler's Theorem](https://en.wikipedia.org/wiki/Euler%27s_theorem)
- [wikipedia - Euler's Totient Function](https://en.wikipedia.org/wiki/Euler%27s_totient_function)
- [cp-algorithms: Euler's Totient Function](https://cp-algorithms.com/algebra/phi-function.html)

## Integración Numérica

- (Wikipedia) <https://en.wikipedia.org/wiki/Numerical_integration>
- (Codeforces [Tasks involving numerical integration](https://codeforces.com/blog/entry/8242)
- (youtube) [Explanation of Simpson's rule \| MIT 18.01SC Single Variable Calculus, Fall 2010](https://www.youtube.com/watch?v=uc4xJsi99bk)
- (youtube) [Simpson's Rule & Numerical Integration](https://www.youtube.com/watch?v=7EqRRuh-5Lk)
- (youtube) [Numerical Integration With Trapezoidal and Simpson's Rule](https://www.youtube.com/watch?v=RTX-ik_8i-k  )
