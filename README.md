# BIENVENIDOS A NEOVIM

# Temario

- [Introducción](#introducción)
- [Desplazamiento en el entorno](#desplazamiento-en-el-entorno)
- [Modos](#modos)
- [Configuraciones iniciales](#configuraciones-iniciales)
- [Copiado y pegado de texto](#copiado-y-pegado-de-texto)
- [Operadores y combinaciones](#operadores-y-combinaciones)
- [Búsquedas](#búsquedas)
- [Configuraciones avanzadas](#configuraciones-avanzadas)
    - [Atajos de teclado](#atajos-de-teclado)
    - [Extensiones](#extensiones)

# Introducción
Aquí va la introducción.

Archivo de configuración: ~/.config/nvim/init.vim
Configuracion avanzada:
    Multiples archivos
    Atajos de teclado
    Extenciones

# Desplazamiento en el entorno
Para poder moverse dentro de Vim o Neovim, se utilizarán las siguientes teclas:
- j : Para poder moverse una línea hacia abajo.
- k : Para poder moverse una línea hacia arriba.
- h : Para poder moverse un caracter hacia la izquierda.
- l : Para poder moverse un caracter hacia la derecha.
- w :
- b :
- e :
- 0 :
- $ :
- % :
- Ctrl + e :
- Ctrl + y :
- Shift + Arriba :
- Shift + Abajo :
- gg :
- G :
- <Numero>G : Moverse de linea

# Modos
Dentro de nuestro entorno existen diferentes modos:

## Normal
Comandos que actuan en modo normal: u , Ctrl + r, x, X, 0, $

## Comando
Teclas para acceder a modo comando: / ? :
- :write
- :quit
- :w
- :q
- :q!
- :wq

## Insertar
Teclas que te envian a insertar: i, I, a, A, o, O

## Visual
Teclas que te ayudan a entrar a visual: v V(V-line)
- v :
- V :
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
    * Ctrl + e (^E) :
    * Ctrl + y (^Y) :

- :%s/<Palabra a buscar>/<Palabra a reemplazar>

# Configuraciones iniciales
Configuraciones que ya tiene Neovim:
- Ctrl + g :

# Copiado y pegado de texto
- s : Que hace
- p : 
- P : 

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
- d$ :
- d% :
- d0 :

### Faltan mas operadores.

# Búsquedas
- /: Cursos en adelante.
- ?: Antes del cursor.
- #: Palabra en específico. 

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
