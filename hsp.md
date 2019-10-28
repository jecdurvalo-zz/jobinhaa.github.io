[Ler em português](readme.md)

## ¿Cómo funciona?

El [Git](https://git-scm.com) es una herramienta muy utilizada en el ambiente de desarollo para control de version.

Ya el [Github](https://github.com) es un sitio que hospeda los archivos/projectos que fueron versionados por el Git(*existen otros sitios que hacen lo mismo, pero el Github es lo mas conocido. Ej: Gitlab, Bitbucket*). Para usarlo es necesario crear una cuenta en el **Github** (personal o de la compania) y instalar el **Git** en su computadora.

No es necesario tener alguna IDE(programa) para hacer el versionamiento, el CMD funciona bien, pero como el terminal del Windows no es muy agradable, indico la utilizacion del [VSCode (Visual Studio Code)](https://code.visualstudio.com).

El VSCode permite tener una mejor visualizacion do que ocurre en su versionamiento y tambien tiene un terminal Unix integrado, asi puede acceder los comandos del Linux sin problemas ツ

### Comandos Linux MUY necesarios
    cd - Navegar entre los archivos
    mkdir - Crear un repositorio
    touch - Crear archivos
    ls - Enumerar los archivos
    clear - Limpiar el terminal

### [GIT] ¿Cuales son las mejores practicas?

- Nunca haga cambios directamente en la branch principal (**master**)
- Tenga siempre una branch local para hacer sus ajustes
- Siempre comente en el *commit* cual cambio hizo 
- Utilize el *Pull request* (tambien conocido como PR) para hacer cambios en la branch principal

**¿Por que toda essa burocracia? R:** Todo mundo puede usar la misma branch a lo mismo tiempo, con esas buenas practicas tenemos certeza que todo que tenemos allá es la version actual y que va a servir de base para todo el equipo. [Mas infos](https://git-scm.com/book/pt-br/v1/Git-Distribu%C3%ADdo-Contribuindo-Para-Um-Projeto)

#### Entendiendo el flujo

![Flujo](https://static.imasters.com.br/wp-content/uploads/2013/10/git-workflow-release-cycle-4maintenance.png)


    Develop [Local] > Release [Local | Temporaly] > Master[Server]

Es importante siempre etiquetar la version de su actualizacion para que podamos saber que tipo de cambio tuvo. **Ej:** Query produccion V1.0.2 

La sequencia de numeros es basado en:
1. Cambios el las características [1]
2. Cambios chiquitos [0]
3. Reparo de bugs [2]


### Estructura de las Branches

- **Develop** - Branch local donde va hacer el desarollo
- **Release** - Branch local | temporaria - despues de hacer la prueba va hacer el commit y esperar la autorizacion del PR
- **Hotfix** - Branch para reparos de errores
- **Master** - Branch principal


### ¿Cual es la diferencia entre crear una branch local y en el server?

*Local branch* - Solo vos va a tener accedo a los cambios

*Server branch* - Cualquier persona que clonó el projecto va tener accedo a branch


#### Dale, quedo claro, y ahora?

### Comandos basicos


Primeros comandos
        git init

        git add [file.txt]
            (Agregar solo un archivo)

        git add .
            (Agregar todo)

        git status
            (Verificar status)

        git rm -r [file.txt]
            (Eliminar un archivo especifico)

        git commit -m "" 
            (Agregar un comentario al finalizar los cambios)


Manejando las branches

        git checkout -b [Nome da branch] 
            (Crea una branch y ya cambia para la misma)

        git branch [Nome da branch]
            (Crea la branch)

        git branch -d [Nome da branch]  
            (Elimina la branch)

        git branch -m
            (Renombra la branch)

        git checkout [Nome da branch]
            (Cambia de branch)

Enviando para el server

        git push [nome do repositorio] 
            (Envia las infos para el server)

        git push [nome do repositorio] --d [Nome da branch] 
            (Elimina una branch del server)

        git clone [url]
            (Clona un repositorio)


Creando Tags y fusionar archivos

        git tag [nome da Tag]
            (Crea Tags)

        git merge [Nome da branch] 
            (Fusionar la branch actual con la que desea)

        git merge [source branch] [target branch] 
            (Fusionar dos branches -- especificando)


Otros comandos

        git stash 
            (Salva los archivos y deja en el estado"WIP", asi puede cambiar de branch sin commit)

        git reset HEAD 
            (Restablecer el stage (elimina los archivos antes del commit)

        git log --oneline
            (Log unificado)

        git diff [source branch] [target branch] 
            (Muestra la diferencia de una branch para otra)

Manejando versiones remotas

        git remote add [nome do repositorio] [url]
            (Agregar una url remota)

        git remote -v 
            (Ver que remoto tienes)

        git remote rm [nome do repositorio] 
            (Eliminar una conexion remota)

        git pull [nome do repositorio] [Nome da branch] 
            (Busca las info actuais)

        git fetch [nome do repositorio] 
            (Sincronizar con el projecto actual)
