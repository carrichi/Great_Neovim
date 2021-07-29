# ¡Bienvenidos a Neovim!

# Temario

- [Introducción](#introducción)
- [Modos](#modos)
    - [Normal](#normal)
    - [Comando](#comando)
    - [Insertar](#insertar)
    - [Visual](#visual)
    - [Reemplazar](#reemplazar)
- [Configuraciones iniciales](#configuraciones-iniciales)
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

- **`j`** : Para poder moverse una línea hacia abajo.
- **`k`** : Para poder moverse una línea hacia arriba.
- **`h`** : Para poder moverse un caracter hacia la izquierda.
- **`l`** : Para poder moverse un caracter hacia la derecha.
- **`w`** : Realiza un salto palabra por palabra.
- **`b`** : Realiza un salto palabra por palabra, pero en sentido inverso.
- **`e`** : Realiza saltos palabra por palabra, pero mediante la última letra de cada palabra.
- **`0`** : Realiza un salto al comienzo de la línea.
- **`$`** : Realiza un salto al fina lde la línea.
- **`%`** : Permite dar saltos entre los caracteres (), [] y {}, siempre saltando a su contraparte (si esta existe).
- **`Ctrl + y`** : Desplaza la pantalla para ver el contenido SUPERIOR.
- **`Ctrl + e`** : Desplaza la pantalla para ver el contenido INFERIOR.
- **`Crtl + b`** ó **`Shift + Arriba`** : Desplaza la pantalla en saltos grandes hacia ARRIBA.
- **`Ctrl + f`** ó **`Shift + Abajo`** : Desplaza la pantalla en saltos grandes hacia ABAJO.
- **`gg`** : Da un salto al inicio del archivo.
- **`G`** : Da un salto al final del archivo.
- **`<Número>G`** : Permite moverte a una línea en específico.

Para realizar movimientos muy concretos dentro de una misma línea:

- **`f<Caracter>`** : Salto al siguiente caracter ingresado. (Se posiciona por encima del caracter buscado)
- **`F<Caracter>`** : Salto al anterior caracter ingresado. (Se posiciona por encima del caracter buscado)
- **`t<Caracter>`** : Da un salto al siguiente caracter ingresado. (Se posiciona por detrás del caracter buscado)
- **`T<Caracter>`** : Moverse al anterior caracter. (Se posiciona por delante del caracter buscado)

Otros comandos que actuan en modo normal:

- **`u`** : Permite deshacer la última acción realizada.
- **`Ctrl + r`** : Permite re-hacer el último comando realizado.
- **`x`** : Permite **CORTAR** el contenido del archivo caracter a caracter en la posición ACTUAL del cursor.
- **`X`** : Realiza la misma función que la tecla "x", pero "corta" el caracter ANTERIOR A LA POSICIÓN del cursor.
- **`<<`** ó **`>>`** : Permite aplicar o quitar una tabulación a la linea en donde se encuentra el cursor.

## Comando
En este modo se realizan instrucciones específicas como búsquedas o ejecución de comandos en Shell. Para poder acceder a este modo es necesario utilizar las teclas: **`/`**, **`?`** ó **`:`**.
- **`:help`** ó **`:h`** : Permite mostrar el manual de usuario. Pero también permite buscar ayuda para comandos específicos.
- **`:write`** ó **`:w`** : Guarda el archivo que se está editando actualmente.
- **`:quit`** ó **`:q`** : Permite salir del editor de texto (sin guardar).
- **`:q!`** : Forza la salida del editor, incluso si ocurrieron cambios en el archivo.
- **`:wq`**, **`:x!`** ó **`ZZ`** : Realiza la acción de "Guardar y salir".
- **`:buffers`** : Permite conocer los archivos que se encuentran abiertos y almacenados en memoria. Saldrá una pequeña dabla en dónde # representa que ya fue abierto el archivo, %a indica que el arhivo se encuentra abierto y modificándose.
- **`:buffer <Número>`** : Permite cambiar a otro archivo indicando el número asignado en el buffer.
- **`:N`** : Permite ir al archivo anterior que esté contenido en el buffer.
- **`:n`** : Permite entrar al siguiente archivo si este existe en el buffer.

Comandos utilizados en situaciones muy específicas:

- **`:e <Archivo>`** : Añade el contenido del Archivo en la línea donde se encuentra posicionado el cursor.
- **`:r <Archivo>`** : Inserta el contenido de un fichero en la linea siguiente a la posición del cursor.

Para cualquier comando de Shell:
- **`:!<Comando de Shell>`** : Permite ejecutar cualquier comando de Shell, como "ls", "echo", "cat", etc.

## Insertar
En este modo es en el que se puede escribir directamente en el contenido del archivo, aquí las teclas ya cumplen su función de escribir caracteres. Para salir de este modo se hará uso de la tecla **Esc**.
Teclas que permiten ingresar al modo Insertar: 

- **`i`** : Para acceder al modo Insertar posicionados ANTES de la última posición del cursor.
- **`I`** : Para acceder al modo Insertar al INICIO DE TODA LA LÍNEA.
- **`a`** : Para acceder al modo Insertar posicionados DESPUÉS de la última posición del cursor.
- **`A`** : Para acceder al modo Insertar al FINAL DE TODA LA LÍNEA.
- **`o`** : Permite acceder al modo Insertar en una nueva LÍNEA INFERIOR.
- **`O`** : Permite acceder al modo Insertar en una nueva LÍNEA SUPERIOR.

## Visual
En este modo se permite seleccionar secciones de texto sin riesgo de modificar el texto. Es principalmente utilizado para sombrear, copiar y cortar contenido del archivo.

Ya teniéndolo activado, cualquier acción de desplazamiento sombreará el texto.

Las teclas para activarlo son:

- **`v`** : Pemite acceder al modo "Visual". 
- **`V`** : Puede identificarse como un "sub-modo" llamado V-line y permite sombrear mediante líneas de código completas.
- **`Ctrl + v`** : (V-block) 
- **`y`** : Permite **copiar** el texto sombreado.
- **`x`** : Permite **cortar** la seleccion sombreada.
- **`c`** : Viene de la palabra "change" y permite cambiar directamente del modo visual al modo insertar.
- **`s`** : Viene de la palabra "subsitute" y permite realizar la sustitución directa de texto, tiene un funcionamiento muy parecido a la tecla "x".
- **`p`** : Viene de la palabra "paste" y permite **pegar** la sección de texto sombreada con el modo visual. este pegado de texto va después del cursor.
- **`P`** : Funcionamiento inverso al de "p", ya que este realiza el mismo pegado de texto pero antes del cursor.

## Reemplazar
Este modo es muy parecido al modo "insertar" pero a diferencia de este, cualquier tecla va a estar **reemplazando** al caracter en el que se encuentre posicionado el cursor.

Existen 2 teclas que permiten reemplazar caracteres:

- **`r`** : Permite reemplazar un solo caracter en la posición donde se encuentre el cursor.
- **`r`** : Permite acceder al modo reemplazar y estará reemplanzando todos los caracteres hasta que se decida salir del modo con la tecla **Esc**.

En el editor de texto, también se pueden realizar el remplazo de caracteres a partir de línea de comandos:

- **`:s/\<Palabra a buscar\>/\<Palabra a reemplazar\>`** : Siguiendo la sintaxis reemplazará LA PRIMER coincidencia que se encuentre en LA LINEA ACTUAL del cursor.
- **`:s/\<Palabra a buscar\>/\<Palabra a reemplazar\>/g`** : Con esta sintaxis se remplazarán TODAS las coincidencias en LA LÍNEA ACTUAL.
- **`:s/\<Palabra a buscar\>/\<Palabra a reemplazar\>/gc`** : Este comando permite reemplazar TODAS las incidencias en la mima línea pero pregunta que se realizará una a una.

Las acciones que se encontrarán para elegir para cada coincidencia son:

    - **`y`** : Para reemplazar la coincidencia sombreada.
    - **`n`** : Para no reemplazar la coincidencia.
    - **`a`** : Para reemplazar todas.
    - **`q`** : Para no reemplazar ninguna.
    - **`l`** : Para reemplazar solo la primera de todas.

- **`:%s/<Palabra a buscar>/<Palabra a reemplazar>`** : Realiza el mismo proceso que los comandos anteriores, pero este estará buscando las coincidencias en TODO EL ARCHIVO.

# Operadores y combinaciones
Algo muy especial de Vim o Neovim es que este permite utilizar los "comandos" de las teclas como operadores, los cuales pueden ser "unidos" para combinar el comportamiento de cada tecla y también pueden ser "multiplicados" por números para repetir cierta cantidad de veces un mismo comando.

- **`cw`** :
- **`ciw`** : 
- **`dw`** : 
- **`<Número>`**
- **`v%`** :
- **`yy`** ó **`Y`** : 
- **`cc`** : Permite cambiar el contenido de una LÍNEA COMPLETA, por lo que elimina todo el contenido de una línea y cambia directamente a modo Insertar.

## Operador "v"
- <Número>v : Numero de palabras seleccionadas.

## Operador "d"
- dw :
- db :
- de :
- dd :
- d$ ó D :
- d% :
- d0 :
- d<Número><Dirección h,j,k,l> :

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
- :b <Número>
- Ctrl + w Ctrl + w
- Ctrl + w_
- Ctrl + w=
- Ctrl + <flecha>

## Gestión de buffers
- :ls
- :new
- :bnext :bn
- :bprevious :bp
- :b <Número> -> Mostrará el buffer en el número indicado.
- :bd -> Cierra el buffer.
- :bd <Número> -> Cierra el buffer indicado.
- :bd!
