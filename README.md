# ¡Bienvenidos a Neovim!

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
- Proximamente:
    - Gestion de pestañas.
	- :tabnew
	- :+tabnew
	- :-tabnew
	- :0tabnew
	- :$tabnew
	- :tabm <Posicion>
	- :tabclose
	- :tabonly
	- :tabe <Nombre de archivo>
    - Gestion de buffers:
	- :ls
	- :new
	- :bnext :bn
	- :bprevious :bp
	- :b <Numero> -> Mostrará el buffer en el número indicado.
	- :bd -> Cierra el buffer.
	- :bd <Numero> -> Cierra el buffer indicado.
	- :bd!
    - Gestión de ventanas:
	- :split
	- :vsplit
	- :hide
	- :only
	- :b <Numero>
	- Ctrl + w Ctrl + w
	- Ctrl + w_
	- Ctrl + w=
	- Ctrl + <flecha>

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
- Crtl + b :
- Ctrl + f : 
- Shift + Arriba :
- Shift + Abajo :
- gg :
- G :
- <Numero>G : Moverse de linea
- t<Caracter> : Moverse al siguiente caracter.
- T<Caracter> : Moverse al anterior caracter.
- f<Caracter> : Salto al siguiente caracter.
- F<Caracter> : Salto al anterior caracter.

# Modos
Dentro de nuestro entorno existen diferentes modos:

## Normal
Comandos que actuan en modo normal: u , Ctrl + r, x, X, 0, $
- u : 
- Ctrl + r :
- x :
- X :
- 0 :
- $ :
- << o >> : 

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
