---
title: Implementación Base
description: Implementación base de Geometría para Programación Competitiva
---

Para trabajar con puntos, vectores, polígonos, etc en programación competitiva vamos a crear una estructura propia basada en la del libro [Handbook of geometry for competitive programmers](https://victorlecomte.com/cp-geo.pdf).

## Operaciones básicas

Partimos definiendo la estructura con la que vamos a trabajar y unas operaciones básicas.

!!! code-cpp " "
    ```cpp
    typedef double T;   // (1)!
    struct pt {
        T x,y;
        pt operator+(pt p) {return {x+p.x, y+p.y};}
        pt operator-(pt p) {return {x-p.x, y-p.y};}
        pt operator*(T d) {return {x*d, y*d};}
        pt operator/(T d) {return {x/d, y/d};}
    };
    ```

    1. :man_raising_hand: Se puede cambiar por `int` o `long long` según sea necesario.

Entonces, podemos crear puntos y operar de la siguiente forma:

!!! code-cpp " "
    ```cpp
    pt a = {1, 2};   // (1)!
    pt b = {3, 4};
    pt c = a + b; // {4, 6}
    pt d = a - b; // {-2, -2}
    pt e = a * 2; // {2, 4}
    pt f = a / 2; // {0.5, 1}
    /*(2)!/*
    ```

    1. :man_raising_hand: Así se creamos un punto. 
    2. :man_raising_hand: Nuestra implementación nos permite operar de forma intuitiva. 

## Operadores de comparación

Como no hay un orden natural para los puntos, vamos a sólo diferenciar cuando son iguales o no.

!!! code-cpp " "
    ```cpp
    bool operator==(pt a, pt b) {return a.x == b.x && a.y == b.y;}
    bool operator!=(pt a, pt b) {return !(a == b);}
    ```

## Imprimir puntos

Para imprimir un punto, vamos a usar definir el operador `<<` para que imprima `(x,y)`.

!!! code-cpp " "
    ```cpp
    ostream& operator<<(ostream& os, pt p) {
        return os << "("<< p.x << "," << p.y << ")";
    }
    ```

Entonces podemos imprimir un punto de la siguiente forma:

!!! code-cpp " "
    ```cpp
    pt a{3,4}, b{2,-1};
    cout << a+b << " " << a-b << "\n"; // (5,3) (1,5)
    cout << a*-1 << " " << b/2 << "\n"; // (-3,-4) (1.5,2)
    ```

## Distancia entre puntos

Para calcular la distancia entre dos puntos, vamos a usar la fórmula de la distancia euclidiana. Primero definimos la norma de un punto:

!!! code-cpp " "
    ```cpp
    T sq(pt p) {return p.x*p.x + p.y*p.y;}
    double abs(pt p) {return sqrt(sq(p));}
    ```

Ahora podemos calcular la distancia entre dos puntos:

!!! code-cpp " "
    ```cpp
    double dist(pt a, pt b) {return abs(a-b);}
    ```

## Conclusiones

Lo presentado en esta entrada es una breve implementación de una estrucutra de puntos que nos ayudará a manejarlos de forma más fluida. En contraste a ocupar `pair<double, double>` y definir todas sus funciones aparte. Esta forma de trabajar nos da una estructura cómoda para llegar y usar, además de expandible.

Pueden agregarle más funcionalidades échando un vistazo a los siguientes códigos:

- [Implementación de Benja](https://github.com/BenjaminRubio/CompetitiveProgramming/blob/master/Material/Geometry/2D.cpp)
- [Implementación de Pablo](https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Geometry/2D.cpp)

## Material consultado

- [Handbook of geometry for competitive programmers](https://victorlecomte.com/cp-geo.pdf).
