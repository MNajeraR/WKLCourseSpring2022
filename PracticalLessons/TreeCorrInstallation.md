# Instalación de TreeCorr
En este documento seguimos la documentacion de TreeCorr (TC) para su instalación. La manera mas facil de instalar TC es via el gestor de packetes _conda_; de hecho es la manera recomendada por los autores de TC. Por otro lado, TC puede instalarse usando el gestor de paquetes _pip_ o incluso compilando el software desde un archivo tar ([ver documentacion de TC](https://github.com/rmjarvis/TreeCorr)). Ademas, recomendamos usar un ambiente virtual para instalar TC en el y los paquetes relalcionados que se necesiten en _CourseSpring2022_.
 
**Nota**: usar _jupyter-notebook_ no es necesario para usar TC, pero es recomendado para estas sesiones.

## Usando Linux
**Una vez instalado _conda_:**

Primero, actualicemos _conda_, mediante la instrucción en la línea de comando:

`conda update conda`

### Crear un ambiente virtual de conda
Usemos la siguientes lineas para crear un _ambiente virtual local_

Da un nombre al ambiente; este nombre aparecera cuando actives el ambiente en la linea de comandos de la terminal. Para esto teclea `envName=TCEnv`

TC depende de una version de _Python_ mayor a 3.x, por eso necesitamos un ambiente con una version de python 3.0 o mas nueva, por ejemplo la versión 3.9. No te preocupes si no la tienes instalada, _conda_ la descargara (si esta disponible) para tu ambiente. Teclea `pythonV=3.9`

Colocar el embiente en un lugar que no olvides, por ejemplo en tu _home_, mediante la instrucción
`envPath="$HOME/$envName"`

Nota: al colocar el ambiente fuera del lugar por defecto tendremos que especificar la nueva direccion al activar el ambiente.

Crea una carpeta en la direccion que elegiste para _envPath_ y crea el ambiente ahi, mediante la instrucción:

`mkdir $envPath && conda create python=$pythonV --prefix "$envPath"`

### Instalacion de TreeCorr
Usa la siguiente linea de comando para instalar TC en $envPath. 

`conda install -c conda-forge treecorr -p $envPath`

Te pedira instalar toda las dependencias para TC, acepta.

#### Instala _jupyter-notebook_y fitsio
Usa la siguiente linea para instalar _jupyter-notebook_

`conda install jupyter-notebook -p $envPath`

### Activar, Desactivar y Remover ambientes vituales:
 - Para activar el ambiente usa `conda activate $envPath$` (debe aprecer el nombre que escogiste, $envPath, al principio tu linea de comando)
 - Para desactivar el ambiente usa `conda deactivate`. Esto volvera a tu configuracion de _bash_ inicial, por lo que dejará de aparecer el $envPath al principio tu linea de comando.
 - Para remover el ambiente virtual usa el siguiente comando `conda env remove -p $envPath`

## Usando Windows
Existen diversas opciones para usar TC en windows (*recomendamos usar _Linux_*):
- Usar [WSL para instalar una terminal con alguna distribucion de _Linux_](https://docs.microsoft.com/en-us/windows/wsl/install) y seguir los pasos anteriores
- Usar [Colab de Google](https://colab.research.google.com) para instalar treecorr en el cuaderno de trabajo con el comando  `pip install treecorr`
## Referencias:
 - TreeCorr's from Mike Jarvis Github:
    https://github.com/rmjarvis/TreeCorr
 - installing conda:
    https://docs.conda.io/projects/conda/en/latest/user-guide/install/index.html
 - conda managing virtual environments: 
    https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html
 - install wsl (on windows) https://docs.microsoft.com/en-us/windows/wsl/install
