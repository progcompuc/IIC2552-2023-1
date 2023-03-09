---
title: Trie String
description: Explicación del algoritmo de Trie String y su implementación en C++.
---

# Trie String

## Introducción

Trie string es una forma de guardar un conjunto de strings. La idea es almacenar los strings en un árbol, donde cada nodo es un carácter. De forma que si seguimos cada camino desde la raíz hasta alguna de sus hoja podamos reconstruir un string del conjunto original.

## Creación del árbol con un ejemplo

La mejor manera de entender este algoritmo es con un ejemplo. Así que veamos cómo hacer con los strings `tree`, `trie`, `algo`, `assoc`, `all` y `also`.

Empezamos con el árbol vacío solo con la raíz.

<center>

``` mermaid
graph TD
    A[root]

style A fill:#6b9cd5,stroke:#333
```

</center>

Luego anexamos el primer string `tree` carácter por carácter.

<center>

``` mermaid
graph TD
    A[root] --> B((t))
    B --> C((r))
    C --> D((e))
    D --> E((e))
    E:::leaf

style A fill:#6b9cd5,stroke:#333
classDef leaf fill:#f96;
```

</center>

!!! note
    Pintamos de naranja los nodos finales (hojas) para indicar que el string termina ahí (asi podemos distinguir strings que son prefijos de otros). Esto se verá en la implementación.

Veamos el siguiente string, `trie`.

1. Revisamos si el nodo `root` tiene un hijo cuyo carácter es igual a `t`.
2. ¡Existe! se revisa si el nodo `t` tiene un hijo cuyo carácter es igual a `r`.
3. ¡Existe! se revisa si el nodo `r` tiene un hijo cuyo carácter es igual a `i`.
4. No existe :( añadimos el string restante `ie` como un camino debajo del nodo `r`.

<center>

``` mermaid
graph TD
    A[root] --> B((t))
    B --> C((r))
    C --> D((e))
    D --> E((e))
    E:::leaf
    C --> G((i))
    G --> H((e))
    H:::leaf

style A fill:#6b9cd5,stroke:#333
classDef leaf fill:#f96;
```

</center>

Procedemos de forma análoga con los demás strings. El árbol quedaría de la siguiente forma:

`tree`, `trie`, `algo`, `assoc`, `all` y `also`.

<center>

``` mermaid
graph TD
    A[root] --> B((t))
    B --> C((r))
    C --> D((e))
    D --> E((e))
    E:::leaf
    C --> G((i))
    G --> H((e))
    H:::leaf
    A[root] --> J((a))
    J --> K((l))
    K --> L((g))
    L --> M((o))
    M:::leaf
    J --> O((s))
    O --> P((s))
    P --> Q((o))
    Q --> R((c))
    R:::leaf
    J --> T((l))
    T --> U((l))
    U:::leaf
    K --> W((s))
    W --> X((o))
    X:::leaf

style A fill:#6b9cd5,stroke:#333
classDef leaf fill:#f96;
```

</center>

!!! note
    Comprobar si un string está o no en el árbol es básicamente el mismo proceso que para añadirlo. Salvo que cuando no coincida un carácter en el camino, se termina la búsqueda.

## Implementación

Pueden encontrar la implementación de trie string en el siguiente [link](https://github.com/Wh4rp/Competitive-Programming/blob/main/Notes/Strings/Trie%20String.h). Con un ejemplo de uso.

Para implementar este algoritmo necesitamos una estructura de datos que nos permita guardar el árbol. Ocuparemos una clase `Trie` que tendrá un nodo raíz, un método `insert` para añadir strings al árbol y un método `find` para buscar strings en el árbol.

!!! code-cpp " "
    ```cpp
    class Trie {
        struct Node {   // (1)!
            char c;
            bool leaf;
            vector<Node*> children;
            Node(char c) : c(c), leaf(false) {}
        };
        Node* root;
    public:
        Trie() : root(new Node('\0')) {}    // (2)!
        void insert(string s) {    // (3)!
            Node* cur = root;
            for (char c : s) {
                bool found = false;
                for (Node* child : cur->children) {
                    if (child->c == c) {
                        cur = child;
                        found = true;
                        break;
                    }
                }
                if (!found) {
                    Node* new_node = new Node(c);
                    cur->children.push_back(new_node);
                    cur = new_node;
                }
            }
            cur->leaf = true;
        }
        bool find(string s) {   // (4)!
            Node* cur = root;
            for (char c : s) {
                bool found = false;
                for (Node* child : cur->children) {
                    if (child->c == c) {
                        cur = child;
                        found = true;
                        break;
                    }
                }
                if (!found) return false;
            }
            return cur->leaf;
        }
    };
    ```

    1. La struct `Node` es una estructura que guarda un carácter, un booleano que indica si es una hoja y un vector de punteros a nodos hijos.
    2. El constructor de la clase `Trie` inicializa el nodo raíz con el carácter nulo.
    3. El método `insert` recibe un string y lo añade al árbol. Se recorre el string carácter por carácter y se busca si el nodo actual tiene un hijo con el carácter actual. Si no existe, se crea un nuevo nodo con el carácter actual y se añade como hijo del nodo actual. Luego se actualiza el nodo actual al nodo recién creado. Al final se marca el último nodo como hoja.
    4. El método `find` recibe un string y busca si está en el árbol. Se recorre el string carácter por carácter y se busca si el nodo actual tiene un hijo con el carácter actual. Si no existe, se retorna `false`. Cuando sale del ciclo, se retorna `true` siempre y cuando el última carácter era una hoja. 

## Material consultado

- [Tries, Patricia Tries — Programación Competitiva CL](https://youtu.be/wv0ADgndMmc?t=3735){:target="_blank"}
- [Trie String — GeeksForGeeks](https://www.geeksforgeeks.org/trie-insert-and-search/){:target="_blank"}
