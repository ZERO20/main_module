# main_module
Test para manejar submodulos.
---
- Para agregar un repositorio como submódulo utilice el comando:
`git submodule add URL_REPOSITORIO`

- Puede especificar parámetros:
~~~
# la rama a utilizar con -b nombre_rama
git submodule add -b develop https://github.com/ZERO20/submodule.git

# el path al final de la url del repositorio
git submodule add -b develop https://github.com/ZERO20/submodule.git submodules/
~~~

El resultado es la creación de un archivo nombrado `.gitmodules` que contiene la configuración de los submódulos:

```
[submodule "submodules/submodule"]
	path = submodules/submodule # ubicación
	url = https://github.com/ZERO20/submodule.git # url del repositorio
	branch = develop # rama a utilizar

```
- Una vez configurado el repositorio principal con sus submódulos se procede a clonar.

Se puede realizar de dos formas:

- clonando el proyecto principal e inicializar los submódulos de forma manual:
```
git clone https://github.com/ZERO20/main_module.git

> git submodule init # incializar el path

Submodule 'submodules/submodule' (https://github.com/ZERO20/submodule.git) registered for path 'submodules/submodule'

> git submodule update # clona los repositorios identificados como submódulos

Cloning into 'path/main_module/submodules/submodule'...
Submodule path 'submodules/submodule': checked out '5ec6efa685b19df8bfc95bd6c26b28a67d7de0ed'


```
- clonando el repositorio principal e indicando que clone los submódulos:

```
git clone --recursive https://github.com/ZERO20/main_module.git
```
Esto clonará todos los submódulos del repositorio manual de forma automática