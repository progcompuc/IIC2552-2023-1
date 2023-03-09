---
title: C++
---

# C++

```cpp title="Ejemplo de Hello World"
#include <bits/stdc++.h> //importa todo
using namespace std; //para no escribir std::

int main()
{
    printf("Hello world\n"); //Usando syntax de C
    cout << "Hello world\n"; //Usando streams de C++
    return 0;
}
```

```cpp title="Ejemplo de Template"
#pragma GCC optimize("Ofast")
#include <bits/stdc++.h>
using namespace std;
// defines
#define rep(i,a,b) for(int i = a; i < b; ++i)
#define invrep(i,b,a) for(int i = b; i >= a; --i)
#define umap unordered_map
#define uset unordered_set
#define ff first
#define ss second
// typedefs
typedef pair<int,int> ii;
typedef unsigned long long int ull;
typedef long long int ll;
// -------------------------------
int main() {
    ios::sync_with_stdio(false); 
    cin.tie(0);
    return 0;
}
```

## Instalando C++
- Windows:
	- [Usando GCC con MinGW](https://code.visualstudio.com/docs/cpp/config-mingw)
	- [MSYS2](https://www.msys2.org/)
- Linux:
	- Debian o Ubuntu (apt)
		```bash title="Usar el comando"
			sudo apt-get install g++
		```
	- Arch Linux (pacman)
		```bash title="Usar el comando"
			sudo pacman -S g++
		```
	- CentOS, Fedora, o RHEL (yum)
		```bash title="Usar el comando"
			sudo yum install gcc-c++
		```
	[Compilar con g++](http://askubuntu.com/questions/61408/what-is-a-command-to-compile-and-run-c-programs)
- Mac:
	- [Installer en OSX](cpp_osx)
	- [Compilar con CLang](http://stackoverflow.com/questions/9148488/how-do-i-compile-c-with-clang)

## Compilando y ejecutando código en C++:
Ejemplo de secuencia de pasos para resolver un problema en C++ en Windows usando la terminal (en Linux/Mac es bien parecido):

- Crear un archivo `example.cpp`
- Escribir un código de C++ válido y guardar.
- Abrir una terminal y navegar a la carpeta donde está el archivo.
- Opción 1:
	- En la terminal, compilar y ejecutar con el comando: 
	```bash
		g++ -std=c++11 example.cpp && a.exe
	```
	- Escribir el input directamente en la terminal
	- El output irá apareciendo poco a poco en la terminal (intercalado con el input)
- Opción 2:
	- Crear un archivo en la carpeta donde están parados llamado input.txt, copiar y pegar el input ahí y guardar.
	- En la terminal, compilar y ejecutar con el comando: 
	```bash
		g++ -std=c++11 example.cpp && a.exe < input.txt
	```
	- el output aparecerá en la misma terminal
- Opción 3:
	- Crear un archivo en la carpeta donde están parados llamado input.txt, copiar y pegar el input ahí y guardar.
	- En la terminal, compilar y ejecutar con el comando: 
	```bash
		g++ -std=c++11 example.cpp && a.exe < input.txt > output.txt
	```
	- el output quedará guardado en el archivo `output.txt`.

## Tutoriales para aprender C++
- (youtube) [Intro a la Programación Competitiva en C++](https://youtu.be/zTUJFG34Tyw) **(<<<< video cortito, recomendado)**
- [C++ for Python Programmers](https://runestone.academy/runestone/books/published/cpp4python/index.html) **(<<<< por si vienes de Python)**
- [C++ Tutorial (SOLO LEARN: EVERYONE CAN CODE)](https://www.sololearn.com/Course/CPlusPlus/)
- <http://www.cplusplus.com/doc/tutorial/>
- <https://www.hackerrank.com/domains/cpp>
- [LearnCpp](http://www.learncpp.com/)
- [Documentación Oficial de C++](http://www.cplusplus.com/reference/)
- (youtube) [Intro a C++](https://youtu.be/pqWsOsfGKA0)
- (youtube) [Estructuras básicas en C++](https://youtu.be/OldL5e5eGmY)
- (youtube) [C++ Programming Video Tutorials For Beginners [ Complete Series ]](https://www.youtube.com/playlist?list=PLfVsf4Bjg79Cu5MYkyJ-u4SyQmMhFeC1C )
- INPUT / OUTPUT:
	- [Yet again on C++ input/output](http://codeforces.com/blog/entry/5217)
	- [¿Qué es mejor para leer input / imprimir output? cin/cout vs printf/scanf](http://www.cplusplus.com/forum/beginner/34165/)
 
## Tips de implementación en C++ (muy útiles en progcomp)
- Cosas útiles que deberían saber de **C++11 (PARA ESCRIBIR CÓDIGOS MÁS CORTOS Y ELEGANTES)**:
	- [Tutorial: C++11 for programming contests](https://codeforces.com/blog/entry/10124)
	- [Learn C++ 11 in 20 Minutes - Part I](https://youtu.be/U6mgsPqV32A)
	- [Learn C++ 11 in 20 Minutes - Part II](https://youtu.be/Lt0ASrloGSE)
- Los beneficios de usar **references** (&) y **pointers** (\*) (**para no copiar todo por valor y así ser más eficientes**):
	 - [Diferencia entre references y pointers explicada](http://www.ntu.edu.sg/home/ehchua/programming/cpp/cp4_pointerreference.html) **(<<<< muy buen artículo, 100% recomendado)**
	 - [geeksforgeeks - Passing vector to a function in C++](https://www.geeksforgeeks.org/passing-vector-function-cpp/)
	 - [geeksforgeeks - When do we pass arguments by reference or pointer?](https://www.geeksforgeeks.org/when-do-we-pass-arguments-by-reference-or-pointer/)   

- [Codeforces - Manejo de Strings en C++](https://codeforces.com/blog/entry/6230) (**buenos tips para cuando tienen que leer input**)
- [Youtube playlist: lista exhaustiva de videos cubriendo muchísimos aspectos de C++](https://www.youtube.com/playlist?list=PLfVsf4Bjg79Cu5MYkyJ-u4SyQmMhFeC1C)
- STL: standard template library (buen material sobre la standard library de C++, **MUY RECOMENDADO**)
	- [Introduction of STL #1: Overview](https://youtu.be/ltBdTiRgSaw)
	- [Introduction of STL #2: Sequence Containers](https://youtu.be/gxZJ5JNuWMY)
	- [Introduction of STL #3: Associative Containers](https://youtu.be/6iyzPed7FrM)
	- [Introduction of STL #4: Unordered Containers](https://youtu.be/NNLvY9O7ufU)
	- [Introduction of STL #5: Iterators and Algorithms](https://youtu.be/vO2AlrBf5rQ)
	- [Introduction of STL #6: Functors](https://youtu.be/shqvSkk8r0M)
	- [Topcoder: power up c++ with the standard template library part 1](https://www.topcoder.com/community/competitive-programming/tutorials/power-up-c-with-the-standard-template-library-part-1/)
	- [Topcoder: power up c++ with the standard template library part 2](https://www.topcoder.com/community/competitive-programming/tutorials/power-up-c-with-the-standard-template-library-part-2/)
	- [Youtube playlist: varios algoritmos de la librería estándar de C++ para llegar y usar](https://www.youtube.com/playlist?list=PLVFrD1dmDdve4h3Shk0uePpXp8JUMM1w5)
- Para **aprender a trabajar con bits** (operaciones bitwise):
	- [Tutorial sobre Bitwise Operators](https://www.cprogramming.com/tutorial/bitwise_operators.html)
	- [¿Qué es bit masking?](https://stackoverflow.com/questions/10493411/what-is-bit-masking)
	- [geeksforgeeks - Bitwise hacks for competitive programming](https://www.geeksforgeeks.org/bitwise-hacks-for-competitive-programming/)
	- [geeksforgeeks - Bit Tricks for competitive programming](https://www.geeksforgeeks.org/bit-tricks-competitive-programming/)
- ¿Qué son y para qué sirven **Structs** y **Classes** en C++?
	- [Advanced C++: Struct Vs. Class](https://youtu.be/qJ4Kzk6mnFc)
	- [Introduction to Structures in C++ CPP Programming Video Tutorial](https://youtu.be/6gg9Xlv35-I)
	- [Buckys C++ Programming Tutorials - 12 - Introduction to Classes and Objects](https://youtu.be/ABRP_5RYhqU)
	- [Structure and Class differences in C++ C ++ Tutorial Mr. Kishore](https://youtu.be/W1f3TelobMg)
	- [CLASSES vs STRUCTS in C++](https://youtu.be/fLgTtaqqJp0)

## C++ Cheat Sheets & Tricks:
- [C++ Cheat Sheet for ACM ICPC ](https://github.com/ntuorangejuice/cheat-sheet)
	- Aquí pueden encontrar un C++ Solution Template (código que uno siempre escribe al comenzar una solución) + MUCHO MUCHO más :)
- [C++ STL cheatsheet for competitive programming](https://gist.github.com/satwikkansal/c959e89161cc60db16b412233177feab)
- [C++ Tricks](https://codeforces.com/blog/entry/15643)
- [C++ tricks for competitive programming (for C++ 11)](https://www.geeksforgeeks.org/c-tricks-competitive-programming-c-11/)
- [C++ Cheat Sheet de Pablo Messina](https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/c%2B%2B_cheat_sheet.cpp)
