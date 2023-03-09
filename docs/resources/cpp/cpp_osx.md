---
title: Install C++ Compiler for OSX
---

# Compiladores de C++ para OSX
## Default
OSX en general ya tiene instalado g++ y clang, esto se puede revisar haciendo lo siguiente en algún terminal ```which g++``` con lo cual debería salir ```/usr/bin/g++```. Igualmente con clang, ```which clang``` y debería salir ```/usr/bin/clang```

## Usando Brew
### ¿Qué es Brew?
Brew es un packet manager para OSX, es fácil de usar. Su página es [esta](https://brew.sh).
### Instalar g++
Cuando uno quiere instalar g++ uno busca gcc
```bash
brew search gcc
```
Con esto aparecen varias opciones, por ejemplo ```gcc@7```. Para instalarlo se usa
```bash
brew install gcc@7
```
Y una vez instalado uno lo usa de la siguiente forma
```bash
g++-7 input_file.cpp
```
