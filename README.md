# ¡Bienvenidos a Neovim!

# Temario

- [Introducción](#introducción)
- [Modos](#modos)
    - [Normal](#normal)
    - [Comando](#comando)
    - [Insertar](#insertar)
    - [Visual](#visual)
    - [Reemplazar](#reemplazar)
- [Combinaciones y multiplicaciones](#combinaciones-y-multiplicaciones)
- [Búsquedas](#búsquedas)
- [Configuraciones básicas](#configuraciones-básicas)
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

### Para sistemas basados en UNIX

```
~/.config/nvim/init.vim
```

### Windows

```
~/AppData/Local/nvim/init.vim
```

Si la ruta no se encuentra puede utilizarse el comando **`:echo stdpath('config')`**.

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
- **`:s/\<Palabra a buscar\>/\<Palabra a reemplazar\>/gc`** : Este comando permite reemplazar TODAS las incidencias en la mima línea pero pregunta que se realizará una a una. Las acciones que se encontrarán para elegir para cada coincidencia son:
    - **`y`** : Para reemplazar la coincidencia sombreada.
    - **`n`** : Para no reemplazar la coincidencia.
    - **`a`** : Para reemplazar todas.
    - **`q`** : Para no reemplazar ninguna.
    - **`l`** : Para reemplazar solo la primera de todas.

- **`:%s/<Palabra a buscar>/<Palabra a reemplazar>`** : Realiza el mismo proceso que los comandos anteriores, pero este estará buscando las coincidencias en TODO EL ARCHIVO.

# Combinaciones y multiplicaciones

Algo muy especial de Vim o Neovim es que este permite utilizar los "comandos" de las teclas como operadores, los cuales pueden ser "unidos" para combinar el comportamiento de cada tecla y también pueden ser "multiplicados" por números para repetir cierta cantidad de veces un mismo comando.

Para realizar una multiplicación solo será necesario realizar lo siguiente: **`<Número><Comando>`**. Esto indica que el Comando se repetirá el Número de veces que le asignemos.

## Multiplicaciones con las teclas de movimiento

A pesar que son solo teclas que nos permiten movernos por el editor estos pueden ser utilizados como operadores para realizar saltos grandes en el archivo:

- **`<N>h`** : Se moverá N caracteres hacia la izquierda.
- **`<N>j`** : El cursor bajará N cantidad de líneas.
- **`<N>k`** : El cursor subiá N cantidad de líneas.
- **`<N>l`** : El cursor se moverá N caracteres a la derecha.
- **`<N>b`** : El cursor dará un salto de N palabras hacia atrás.
- **`<N>e`** : El cursor dará un salto de N palabras hacia adelante. (termina en el último caracter de la última palabra).

## Combinaciones con la tecla "c"

Viene de la palabra "change" y puede realizar cambios al texto para eliminar contenido y dar un salto al modo Insertar.

- **`cw`** : Con el significado de "Change word", permite eliminar una palabra y activar el modo insertar. **Atención**: Si se utiliza en medio de una palabra será del CURSOR EN ADELANTE.
- **`ciw`** : Significa "Change inner word" y permite eliminar una palabra (sin importar la posición del cursor) para después activar el modo Insertar.
- **`cc`** : Permite cambiar el contenido de una LÍNEA COMPLETA, por lo que elimina todo el contenido de una línea y cambia directamente a modo Insertar.

## Combinaciones con la tecla "v"

Combinaciones para sombrear contenido de forma más rápida.

- **`v0`** : Sombrea el contenido desde el cursor hasta EL INICIO de la línea.
- **`v$`** : Sombrea el contenido desde el curso hasta el FINAL de la línea.
- **`v%`** : Sombrea desde el cursor hasta el paréntesis, corchete o llave más cercana. SOLO SI LA CONTRAPARTE EXISTE.

## Combinaciones con la tecla "d"

- **`dw`** : Significa "Delete word" y su función es eliminar palabras del cursor en ADELANTE.
- **`<N>dw`** : Al igual que el comando "dw" pero realizando una repetición de N veces.
- **`db`** : Permite eliminar palabras en función de los saltos que realiza el comando "b".
- **`de`** : Permite eliminar palabras en función de los saltos que realiza el comando "e".
- **`d$`** ó **`D`** : Esta combinación permite eliminar el contenido de una línea desde el cursor hasta EL FINAL DE LA LÍNEA.
- **`d0`** : Permite eliminar el contenido desde el cursor hasta EL COMIENZO de la línea.
- **`d%`** : Permite eliminar el contenido desde el cursor hasta el paréntesis, conchete o llave más cercana. SOLO SI EXISTE SU CONTRAPARTE.
- **`dd`** : Permite cortar una LÍNEA COMPLETA.
- **`<N>dd`** : Permite cortar N líneas completas.
- **`d<N><Dirección h,l>`** : Permite eliminar N caracteres en la dirección ingresada.
- **`d<N><Dirección j,k>`** : Permite eliminar N+1 líneas en la dirección ingresada. Contando la línea que contiene al cursor.

## Combinaciones con la tecla "y"

- **`yy`** ó **`Y`** : Permite copiar una línea entera, la línea que contiene al cursor.
- **`<N>yy`** ó **`<N>Y`** : Permite copiar N líneas. De la línea que contiene al cursor HACIA ABAJO.

# Búsquedas

En todo editor de texto es necesario buscar palabras, para realizarlas en Vim o Neovim se tienen 3 alternativas:

- **`/`** : Permite realizar búsquedas desde la línea del cursor y su primer coincidencia la buscará por DEBAJO de la línea del cursor.
- **`?`** : Permite realizar búsquedas desde la línea del cursor y su primer coincidencia la buscará por ENCIMA de la línea del cursor.
- **`#`** : Sombrea la palabra en la que se encuentre el cursor y muestra sus coincidencias.

Después de realizar las búsquedas, saldrán sombreadas las coincidencias, pera moverse sobre los resultados se utilizan los siguientes comandos:
- **`n`** : Permite saltar al siguiente resultado.
- **`N`** : Permite saltar al resultado anterior.

# Configuraciones básicas

- **`set number`** : Habilita los numeros de línea del lado izquierdo del editor.
- **`syntax on`** : Habilita el reconocimiento de sintaxis para diferentes lenguajes, lo cual permite activar los colores. *
- **`syntax enable`** : Realiza el mismo funcionamiento que "syntax on". * 
- **`set tabstop=4`** : Permite configurar la cantidad de expacios en la tabulación.
- **`set sw=4`** : Para indicar la cantidad de renglones para la tabulación (sangría).
- **`set autoindent`** : Permite añadir el autoidentado. *
- **`set clipboard=unamedplus`** : Permite compartir el copiado y cortado de texto con el del sistema operativo.
- **`set relativenumber`** : Añade los números relativos para indicar el número de líneas de distancia desde la línea actual. Es utilizada esta opción para realizar saltos.
- **`set mouse=a`** : Para activar el reconocimiento del ratón dentro del editor.
- **`set numberwidth=<N>`** : Permite añadir una cantidad N de espacios entre el contenido del archivo y los números del lado izquierdo.
- **`set showcmd`** : Permite ver los comandos escritos en el modo Comando. **
- **`set ruler`** : 
- **`set cursorline`** : Añade una línea horizontal a la linea activa para identificarla.
- **`set encoding=utf-8`** : Para indicar una codificación en el editor. *
- **`set showmatch`** : Para indicar las coincidencias en las búsquedas. *
- **`set noshowmode`** : Configuración para que no se muestre el modo que se encuentra activo.

# Configuraciones avanzadas

## Multiples archivos

- **`so <Ruta a archivo>`**

## Atajos de teclado

**`<space>w :w`**
**`<space>q :q`**
**`<space>n :noh`**
**`<space>t :nerdtree`**

## Extensiones

Al igual que muchos otros editores de texto, a Neovim se le pueden agregar extensiones para que resulte ser una herramienta más completa.

Para aplicar instalar extensiones es necesario utilizar un gestor de extensiones, en esta guía se utilizará el gestor **Vim-Plug**.

Para instalarlo has click [aquí](https://github.com/junegunn/vim-plug).

Después de haber instalado el gestor, tendremos a nuestra disposición nuevos comandos en el editor, algunos de estos son:

- **`:PlugInstall`** : Permite instalar las extensiones descritas en nuestro archivo de configuración.
- **`:PlugClean`** : Elimina las carpetas de las extensiones que no son utilizadas.
- **`:PlugUpdate`** : Para buscar actualizaciones de las extenciones utilizadas.

Para empezar a instalar extensiones se deben agregar las siguientes líneas a nuestro archivo de configuración:

```vim
call plug#begin('<Ruta a carpeta que guardará la información de los plugins>')

Plug '<autor>/<nombre del plugin>'

call plug#end()
```

Después de haber indicado las extensiones a utilizar deberá utilizarse el comando **`:PlugInstall`** y ¡listo! Las extensiones se encuentran listas para utilizar.

#### Esquemas de color

Dentro del editor de código es posible cambiar los esquemas de color y para realizar este cambio es necesario añadir la siguiente sentencia al archivo de configuración principal (init.vim):

- **`colorscheme <nombre>`**

Para algunos esquemas de color será requerido contar con una terminal de 256 colores, por lo tanto, se recomienda añadir lo siguiente:

```vim
if (has("nvim"))
    let $NVIM_TUI_ENABLE_TRUE_COLOR=1
endif

if (has("termguicolors"))
    set termguicolors
endif
```

Esquemas recomendados:

- 'joshdick/[onedark]().vim'
- 'articicestudio/[nord-vim]()'
- 'cocopon/[iceberg]().vim'

#### Barra flotante de información

- **Lightline** : Integra una barra de información en el editor.

- 'itchyny/[lightline.vim](https://github.com/itchyny/lightline.vim)' :  

Complementos:

- 'dense-analysis/[ale](https://github.com/dense-analysis/ale)' : 
- 'maximbaz/[lightline-ale](https://github.com/maximbaz/lightline-ale)' : 
- 'hallzy/[lightline-onedark](https://github.com/hallzy/lightline-onedark)' : theme

#### Visor de archivos

- **Nerdtree** : 

- 'preservim/[nerdtree](https://github.com/preservim/nerdtree)'

Opciones
m - Mostrar alternativas

#### Pantalla dividida

- **Navigator** : Con el t y moverse con el Ctrl + h, j, k, l

- 'christoomey/[vim-tmux-navigator](https://github.com/christoomey/vim-tmux-navigator)' :

#### Uso de Git

- 'tpope/[vim-fugitive](https://github.com/tpope/vim-fugitive)' :

# Neovim nivel avanzado

Esta parte aún se encuentra en desarrollo...

## Gestión de pestañas 

- **`:tabnew`** :
- **`:+tabnew`** :
- **`:-tabnew`** :
- **`:0tabnew`** :
- **`:$tabnew`** :
- **`:tabm <Posicion>`** :
- **`:tabclose`** :
- **`:tabonly`** :
- **`:tabe <Nombre de archivo>`** :

## Gestión de ventanas

- **`:split`** :
- **`:vsplit`** :
- **`:hide`** :
- **`:only`** :
- **`:b <Número>`** :
- **`Ctrl + w Ctrl + w`** :
- **`Ctrl + w_`** :
- **`Ctrl + w=`** :
- **`Ctrl + <flecha>`** :

## Gestión de buffers

- **`:ls`** :
- **`:new`** :
- **`:bnext`** ó **`:bn`** :
- **`:bprevious`** ó **`:bp`** :
- **`:b <Número>`** : Mostrará el buffer en el número indicado.
- **`:bd`** : Cierra el buffer.
- **`:bd <Número>`** : Cierra el buffer indicado.
- **`:bd!`** :
