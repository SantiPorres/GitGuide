> # Guía rapida de Git

Esta es una guía rapida para el uso de Git.  
Puedes descargarlo desde [aquí](https://git-scm.com/).
> Tabla de contenido

* [Primeros pasos](#primeros-pasos)
* [Conceptos basicos](#conceptos-basicos)
* [Comandos](#comandos)
* [Herramientas](#herramientas)

> # Primeros pasos

  Una vez instalado Git, puedes utilizarlo desde la Linea de comandos o desde el [Git Bash](#git-bash-1) 
  y establecer los valores de configuración ejecutando:
  ```
  git config --global user.name "Tu nombre de usuario"
  ```
  ```
  git config --global user.email "El email de tu cuenta de GitHub o Gitlab"
  ```
  > [!NOTE]
  > Establecer los valores de configuracion es importante para el uso de plataformas de alojamiento (GitHub, GitLab, ...), y para identificar la autoría de los [commits](#commit).

  ---

  Visualizar tu version de Git utilizando:
  ```
  git -v
  ```
---
> # Conceptos basicos

* ## Repositorio
    Un repositorio es un espacio en el que se almacenan y gestionan los archivos de un proyecto. Este repositorio puede ser local (en tu maquina) o remoto (en un servidor).

* ## Commit
    Un commit es un conjunto de cambios realizados en los archivos que almacena el repositorio. Este conjunto de cambios viene acompañado de un titulo y una descripción.

* ## Branch (rama)
    Una rama es una linea de trabajo independiente que se genera de otra rama. De este modo, el equipo de desarrollo evita trabajar sobre el mismo codigo al mismo tiempo.  
    ### Tipos de ramas
    Existen dos tipos de ramas (principales y auxiliares).  
    Las ramas principales son:
    * master o main: rama de producción.
    * development: rama dedicada a integrar y probar cambios antes de fusionarlos con la rama de producción.

    Las ramas auxiliares son:
    * feature: rama dedicada a la adición o modificación de características del proyecto.
    * release: rama en la cual se realizan las pruebas finales y se prepara el codigo para el lanzamiento de una nueva versión.
    * hotfix: rama en la cual se arreglan bugs de producción que deben ser solucionados lo más pronto posible.

> [!WARNING]
> No trabajar nunca sobre la main o master!

* ## Merge
    Un merge es el proceso en el que se fusionan dos ramas, es decir, se combinan los cambios que se hicieron en dos ramas.

* ## Conflictos de Merge
    Los conflictos de merge ocurren cuando el proceso de fusion mencionado no se puede llevar a cabo. Esto puede ocurrir porque Git no puede identificar cuales son los cambios que deben persistir y en ese caso, el desarrollador que este haciendo el merge deberá solucionarlo manualmente.
---
> # Comandos

* ## Clonar un repositorio
    ```
    git clone [URL remota]
    ```

* ## Visualizar el repositorio remoto
    ```
    git remote -v
    ```
    Este comando te muestra la URL del repositorio remoto.

* ## Visualizar ramas del repositorio
    ```
    git branch
    ```
    Este comando lista las ramas del repositorio y resalta la rama en la que estas actualmente ubicado.

* ## Crear una nueva rama
    ```
    git checkout -b [nombre de la nueva rama]
    ```
    Este comando creará una nueva rama a partir de la que estes utilizando en ese momento y te situará en ella automaticamente.

* ## Traer los cambios del repositorio remoto al local
    ```
    git pull origin [rama de la cual traer cambios]
    ```
    Este comando trae los ultimos cambios realizados en el repositorio remoto. Puedes poner la rama en la que estas actualmente trabajando, o también puedes traer los cambios de otra rama a la tuya.

    #### origin se refiere a la [URL remota](#visualizar-el-repositorio-remoto)


* ## Visualizar el estado actual del repositorio local
    ```
    git status
    ```
    Este comando listará los archivos modificados, eliminados y añadidos, asi como los archivos no preparados para commit, los que si lo están y los archivos no rasterados.
    
    #### (staging area: area de preparación)
    #### (untracked files: archivos no rastreados)

* ## Visualizar los cambios realizados en cada archivo
    ```
    git diff [direccion del cambio]
    ```
    Te mostrará en rojo el antes y en verde el después.

* ## Preparar los cambios para subirlos al repositorio remoto
    ```
    git add [direccion del cambio]
    ```
    Con este comando podrás añadir el cambio especificado al staging area, permitiendote hacerle commit para comentar el motivo o descripción del cambio.  

    Si quieres añadir todos los cambios, puedes utilizar:
    ```
    git add .
    ```

* ## Comentar los cambios del staging area (area de preparación)
    Este comando toma los cambios del staging area y los guarda permanentemente en el repositorio local, junto a un titulo y descripción (la ultima es opcional).
    ```
    git commit -m "Titulo del conjunto de cambios que realizaste"
    ```
    o
    ```
    git commit
    ```
    La diferencia entre estos dos es que el primero te permitirá añadir solo el titulo del commit, mientras que el segundo abre Vim para que puedas añadir tanto un titulo, como una descripción.

    #### Los commits de Git siguen una [convención](https://medium.com/@naandalist/creating-a-git-commit-message-convention-for-your-team-acb4b3edfc44).


* ## Visualizar todos los commits
    ```
    git log
    ```
    Este comando te muestra el historial de commits.

* ## Enviar los cambios locales al repositorio remoto
    ```
    git push origin [rama actual]
    ```
    Despues de confirmar los cambios con el git commit, se utiliza este comando para enviarlos al repositorio remoto.
    
    #### origin se refiere a la [URL remota](#visualizar-el-repositorio-remoto)

> [!WARNING]
> No hacer nunca ```git push --force```!


---
> # Herramientas

* ## GitLens

* ## Git Bash
---
