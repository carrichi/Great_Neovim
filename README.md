# ¡Bienvenidos a Neovim!

# Temario

- [Introducción](#introducción)
- [Modos](#modos)
    - [Normal](#normal)
    - [Comando](#comando)
    - [Insertar](#insertar)
    - [Reemplazar](#reemplazar)
    - [Visual](#visual)
- [Configuraciones iniciales](#configuraciones-iniciales)
- [Copiado y pegado de texto](#copiado-y-pegado-de-texto)
- [Operadores y combinaciones](#operadores-y-combinaciones)
- [Búsquedas](#búsquedas)
- [Configuraciones avanzadas](#configuraciones-avanzadas)
    - [Atajos de teclado](#atajos-de-teclado)
    - [Extensiones](#extensiones)
- [Neovim nivel avanzado](#neovim-nivel-avanzado)
    - [Gestión de pestañas](#gestión-de-pestañas)
    - [Gestión de ventanas](#Gestión-de-ventanas)
    - [Gestión de buffers](#gestión-de-buffers)

# Introducción
[Neovim](https://neovim.io/) es un editor de texto de código abierto el cual tiene una mejor compatibilidad y rendimiento ante su sucesor Vi IMprove (Vim).

A comparación de Vim, Neovim utiliza un archivo de configuración distinto, la ruta a este se encuentra en: 

```
~/.config/nvim/init.vim
```

Una de las características especiales de este editor es que se maneja mediante MODOS, los cuales los más representativos son:

* Modo normal
* Modo comando
* Modo insertar
* Modo reemplazar

# Modos
Dentro del editor de código, podemos disponer de Modos, el cuál cada uno tendrá funciones específicas.

## Normal
En este modo es el que se mantiene activo la mayoría del tiempo y es el modo que siempre está por enmedio del cambio entre un modo y otro. **Cuando este modo se encuentra activo, todas las teclas ejecutan acciones específicas.** 

Entre estas acciones están las teclas de desplazamiento:

- j : Para poder moverse una línea hacia abajo.
- k : Para poder moverse una línea hacia arriba.
- h : Para poder moverse un caracter hacia la izquierda.
- l : Para poder moverse un caracter hacia la derecha.
- w : Realiza un salto palabra por palabra.
- b : Realiza un salto palabra por palabra, pero en sentido inverso.
- e : Realiza saltos palabra por palabra, pero mediante la última letra de cada palabra.
- 0 : Realiza un salto al comienzo de la línea.
- $ : Realiza un salto al fina lde la línea.
- % : Permite dar saltos entre los caracteres (), [] y {}, siempre saltando a su contraparte (si esta existe).
- Ctrl + y : Desplaza la pantalla para ver el contenido SUPERIOR.
- Ctrl + e : Desplaza la pantalla para ver el contenido INFERIOR.
- Crtl + b ó Shift + Arriba: Desplaza la pantalla en saltos grandes hacia ARRIBA.
- Ctrl + f ó Shift + Abajo: Desplaza la pantalla en saltos grandes hacia ABAJO.
- gg : Da un salto al inicio del archivo.
- G : Da un salto al final del archivo.
- <Numero>G : Permite moverte a una línea en específico.

Para realizar movimientos muy concretos dentro de una misma línea:

- f<Caracter> : Salto al siguiente caracter ingresado. (Se posiciona por encima del caracter buscado)
- F<Caracter> : Salto al anterior caracter ingresado. (Se posiciona por encima del caracter buscado)
- t<Caracter> : Da un salto al siguiente caracter ingresado. (Se posiciona por detrás del caracter buscado)
- T<Caracter> : Moverse al anterior caracter. (Se posiciona por delante del caracter buscado)

Otros comandos que actuan en modo normal:

- u : Permite deshacer la última acción realizada.
- Ctrl + r : Permite re-hacer el último comando realizado.
- x : Permite "cortar" el contenido del archivo caracter a caracter en la posición ACTUAL del cursor.
- X : Realiza la misma función que la tecla "x", pero "corta" el caracter ANTERIOR A LA POSICIÓN del cursor.
- << o >> : Permite aplicar o quitar una tabulación a la linea en donde se encuentra el cursor.

## Comando
Teclas para acceder a modo comando: / ? :
- :help :h
- :write
- :quit
- :w
- :q
- :q!
- :wq, :x! o ZZ :
- :n
- :N
- :buffers
    - Lo que indica el #, %a y si esta vacio.
- :buffer <Numero>

Comandos utilizados en situaciones muy específicas:

- :e
- :r

Para cualquier comando de Shell:
- !<Comando de Shell>

## Insertar
Teclas que te envian a insertar: i, I, a, A, o, O

## Visual
Teclas que te ayudan a entrar a visual: v V(V-line)
- v :
- V :
- Ctrl + v (V-Block) :
- c :
- cc :
- x : Cortar la seleccion

## Reemplazar
Teclas que te permiter reemplazar texto:
- r : 
- R : 
- :s/<Palabra a buscar>/<Palabra a reemplazar>
- :s/<Palabra a buscar>/<Palabra a reemplazar>/g
- :s/<Palabra a buscar>/<Palabra a reemplazar>/gc : Preguntando confirmacion
    * y : Para reemplazar la coincidencia sombreada.
    * n : Para NO reemplazar la coincidencia.
    * a : Para reemplazar TODAS.
    * q : Para no reemplazar NINGUNA.
    * l : Para reemplazar solo la primera de todas.
    * Ctrl + e (^E) : Desplazar la pantalla para ver el contexto
    * Ctrl + y (^Y) : Desplazan la pantalla para ver el contexto

- :%s/<Palabra a buscar>/<Palabra a reemplazar>

# Copiado y pegado de texto
- s : Que hace
- p : 
- P : 
- yy ó Y : 

# Operadores y combinaciones
- cw :
- ciw : 
- dw : 
- <Numero>
- v% :

## Operador "v"
- <Numero>v : Numero de palabras seleccionadas.

## Operador "d"
- dw :
- db :
- de :
- dd :
- d$ ó D :
- d% :
- d0 :
- d<Numero><Dirección h,j,k,l> :

### Faltan mas operadores.

# Búsquedas
- /: Cursos en adelante.
- ?: Antes del cursor.
- #: Palabra en específico. 

# Configuraciones básicas
- set number (Habilita los numeros)
- syntax on (Habilita colores) Creo que ya la tiene.
- set tabstop=4 (configra el TAB)
- set autoindent (ya la tiene)

# Configuraciones iniciales
Configuraciones que ya tiene Neovim:
- Ctrl + g :

# Configuraciones avanzadas
## Multiples archivos
so

## Atajos de teclado
<space>w :w
<space>q :q
<space>n :noh
<space>t :nerdtree

## Extensiones
- Nerdtree : m - Mostrar alternativas
- Navigator : Con el t y moverse con el Ctrl + h, j, k, l

# Neovim nivel avanzado

Esta parte aún se encuentra en desarrollo...

## Gestión de pestañas 
- :tabnew
- :+tabnew
- :-tabnew
- :0tabnew
- :$tabnew
- :tabm <Posicion>
- :tabclose
- :tabonly
- :tabe <Nombre de archivo>

## Gestión de ventanas
- :split
- :vsplit
- :hide
- :only
- :b <Numero>
- Ctrl + w Ctrl + w
- Ctrl + w_
- Ctrl + w=
- Ctrl + <flecha>

## Gestión de buffers
- :ls
- :new
- :bnext :bn
- :bprevious :bp
- :b <Numero> -> Mostrará el buffer en el número indicado.
- :bd -> Cierra el buffer.
- :bd <Numero> -> Cierra el buffer indicado.
- :bd!
