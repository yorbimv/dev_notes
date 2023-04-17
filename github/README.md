# Git

## ¿Que es git?

- Un sistema de control de versiones distribuidos.

  - Un sistema de control de versiones nos permite llevar un historial de los cambios.
## Tabla de contenidos

- [Instalación](#instalación)
- [Configuracion inicial](#configuración-inicial)
- [Comandos git](#comandos-git)
- [Comandos git-log](#comandos-git-log)
- [Comandos checkout](#comandos-checkout)
- [Otros Comandos](#otros-comandos)


## Instalación 

Mac
```
brew install git
```

## Configuración inicial

<details>
  <summary>Desde la web</summary>
  
1. Crear un repositorio en github  `/mirepo`
  
2. Crear e ingresar en la carpeta de nuestro proyecto en nuestro equipo
  
3. Abrir una terminal desde la ubicación de la carpeta
  
4. Copiar y ejecutar el enlace generado de github en nuestra terminal
```
git remote add origin https://github.com/yorbimv/mirepo.git 
```

  * Si solicita credenciales, ingresarlas

    - Usuario: tuUsuario
    - Password: token
        - [`https://github.com/settings/tokens`](https://github.com/settings/tokens)
5. En la terminal nos aparece una rama llamada master
  * Se recomienda crear una rama main y empezar a trabajar desde ahi.
</details>

<details>
<summary>Desde la PC</summary>
  
1. Crear una carpeta con el nombre similar al del repositorio
   *  
   ```
   mkdir mirepo
   ```
  
2. Ingresar a la carpeta creada
   * Ejecutar
      * 
      ```
      git init
      ```
   * Se crean los archivos necesarios para poder sincronizarse con nuestro repositorio  
  
3. Desde github, crear una repo
  
4. Ejecutar los comandos como indican las instrucciones de github para asociar la repo con nuestra carpeta en nuestro equipo.

</details>

### Configurar tu nombre de usuario en Git en tu equipo
Git utiliza un nombre de usuario para asociar las confirmaciones con una identidad.

El nombre de usuario de Git no es tu mismo nombre de usuario de GitHub.

* Usuario actual de git
```
git config user.name
```
* Correo actual de git
```
git config user.email
```

<details>
<summary>Ejemplo:</summary> 

* Cambiar de usuario git en nuestro equipo

  * Si por alguna razon, se desea trabajar con otro usuario de git:
    * Se debe configurar usuario, correo:

      * Usar nombre y correo global, aplica para todos los repositorios que se va a trabajar en nuestro equipo

      ```
      git config --global user.name yorbimv
      ```
      ```
      git config --global user.email yorbimv@correo.com
      ```


      * Configurar tu nombre  y correo de usuario de Git para un repositorio único

      ```
      git config user.name "Jorge Meneses"
      ```
      ```
      git config user.email jorgemeneses@correo.com
      ```  
</details>

## Comandos git

| Comando           | Descripción                          | Ejemplo |
|     :---:         |     :---                             | :--- | 
| ```git status```  | Muestra el estado actual, permite ver los cambios pendientes o aplicados |      ```git status```    |
| ```git clone```   | Se usa para clonar, copia un repositorio local o remoto ssh o https    |```git clone    git@github.com:mouredev/hello-git.git  ```    |
|```git add ```| Agrega todos los cambios que se hayan aplicado en todos los ficheros| ```git add . ``` \| ```git add *.py ``` |
|```git commit -m```| Una breve descripción de los cambios aplicados| ```git commit -m “este es mi primer commit”```|
|```git push ```|Subir cambios a la repo|```git push``` |
|```git pull```|Actualiza ficheros desde el repositorio remoto|```git pull``` |


## Comandos git-log

| Comando           | Descripción                                     | Ejemplo |
|     :---         |     :---                                       |     :--- | 
|```git log```      |Revisar los log con información detallada        |git log|
|```git log --graph```|Revisar los log con información detallada con gráficos||
|```git log --graph --pretty=oneline```|Revisar los log con información detallada con gráficos, pero con menos información||
|```git log --graph --decorate --all --online``` |Revisar los log con información completa y reducida | Se crea un alias para log ```gittree```|



## Comandos checkout
| Comando           | Descripción                                     | Ejemplo |
|     :---         |     :---                                       |     :--- | 
|```git checkout <nombreArchivo.ext>```|Regresa  al último estado que se guardó en git|Se puede usar para regresar a un commit anterior, a un archivo o aun id|
|```git reset```|Regresa a todos al último estado guardado en git||
|```git diff ```|Muestra los cambios que se hayan aplicado en ficheros, branchs, commits, etc| ```git diff HEAD``` \| ```git diff archivo.ext```\| ```git diff id_log id_log2 ```|


## Otros comandos

#### Alias
| Comando a convertir en alias           | Descripción                                   | Ejemplo |
|     :---         |     :---                                       |:---|
|```git config --global alias.treegit "log --graph --decorate --all --oneline”```| Se crea alias ```treegit```|```git treegit```|

#### Branch 

| Comando                     | Descripción                     | Ejemplo                           |
|     :---                    |     :---                        |     :---                          | 
|```git branch nuevaRama```   |Crea una rama nueva              |```git branch main```              |
|```git checkout -b```        |Crea y cambia a una rama nueva   | ```git checkout -b ramaNueva```   |
|```git switch -c  ```        |Crea y cambia a una rama nueva   |```git switch -c ramaNueva```      |
|```git branch```             |Lista de todas las branch        |```git branch```                   |
|```git switch```             |Cambia de rama                   |```git switch main```              |
|```git branch -m```          |Renombrar branch                 |```git branch -m nuevoNombreBranch```|
|```git branch -d ```         |Eliminar branch                  |```git branch -d ramaAEliminar```  |
|```git merge```              |Fusionar ramas                   |```git merge <nombreBranch>```     |

Fusionar ramas
* Posicionarte en la rama main antes de fusionar


Ver cambios antes de hacer un pull

``` git fetch --dry-run ```

Ir a un cambio en específico

```git checkout id ```

Ir a cierto punto del historial de la rama

```git reset —hard```

Historial completo

```git reflog```

### VS Code

Abrir VS desde la carpeta de terminal

```code .```


### Tags

Los tags se usan normalmente para indicar la version

Crear un tag

```git tag "Nombre_de_etiqueta```

Cambiar a branch con tag

```git checkout tags/login_v1```

Al cambiar de esta forma, podemos realizar cambios sin perjudicar la rama actual, en caso de conservar los nuevos cambios, se crea una rama nueva con 

```git switch -c <nombre-de-nueva-rama>```

### Git stash

Su función nos sirve para guardar esos cambios sin subirlos a producción, es decir podemos “salvar” esos cambios para poder cambiar de rama y seguir desarrollando.
```git stash```
<details>
<summary>
Ejemplo:
</summary>
Tenemos una rama main, una rama A y una rama B
 
En la rama A, tenemos un archivo login.py incompleto, se nos pide que se arregle un archivo en la rama b.

Al intentar hacer el cambio de rama, no es posible hacer el cambio sin antes hacer un commit en la rama A

Usamos ```git stash``` para guardar el cambio en la rama A, ahora ya es posible realizar el cambio a la rama B

Una vez solucionado el archivo en la rama B, nos cambiamos a la rama A, pero notaremos que no esta nuestros cambios guardados.

Para visualizar el cambio guardado, se ejecuta 
``` git stash pop ```

Ahora podemos seguir trabajando.

* Si queremos ver los cambios stash
```git stash list ```
* Si queremos eliminar los cambios salvados
```git stash drop```

</details>


