
[Leer en español](https://github.com/jobinhaa/jobinhaa.github.io/blob/master/hsp.md)

## Como funciona?

O [Git](https://git-scm.com) é uma ferramenta muito utilizada no ambiente de desenvolvimento para fazer o versionamento dos arquivos.

Já o [Github](https://github.com) é o site que hospeda os arquivos/projetos que estão sendo versionados pelo Git (*existem outros que fazem a mesma coisa em cima do Git mas esse é o mais utilizado. Ex: Gitlab, Bitbucket*). Para utilizá-lo é necessário ter uma conta no **Github** (pessoal ou da empresa) e o **Git** instalado na sua máquina.

Não é obrigatório ter alguma IDE(programa) para fazer o versionamento, o CMD já funciona, no entanto como o terminal do Windows não é tão legal, indico a utilização do [VSCode (Visual Studio Code)](https://code.visualstudio.com).

O VSCode te permite ter uma visualização um pouco melhor do que está acontecendo e também possui o terminal integrado com Unix, dessa forma conseguimos usar os comandos do Linux ツ

### Comandos Linux super necessários
    cd - Navegar entre pastas
    mkdir - Criar repositórios
    touch - Criar arquivos
    ls - Listar arquivos
    clear - Limpar terminal

### [GIT] Quais são as boas práticas?

- Nunca faça alterações diretamente na branch principal (**master**)
- Tenha sempre uma branch local para fazer seus ajustes
- Sempre comente no *commit* o que você alterou 
- Utilizar o *Pull request* (também conhecido como PR) para fazer alterações na branch principal

**Por que toda essa burocracia? R:** Todo mundo pode estar usando a mesma branch ao mesmo tempo, dessa forma temos que ter certeza que o que temos ali é a versão atualizada que servirá como base para todo o time. [Mais infos](https://git-scm.com/book/pt-br/v1/Git-Distribu%C3%ADdo-Contribuindo-Para-Um-Projeto)

#### Entendendo o fluxo

![Fluxo](https://static.imasters.com.br/wp-content/uploads/2013/10/git-workflow-release-cycle-4maintenance.png)


    Develop [Local] > Release [Local | Temporaly] > Master[Server]

É importante sempre "tagear" a versão da sua atualização para que possamos saber qual tipo de mudança tivemos. **Ex:** Query produção V1.0.2 

A sequencia de números é com base em:
1. Mudanças nas funcionalidades [1]
2. Mudanças pequenas sem alteração na funcionalidade [0]
3. Conserto de Bug [2]


### Estrutura das Branches

- **Develop** - Branch local onde você desenvolve
- **Release** - Branch local finalizada e testada só aguardando a aprovação do PR
- **Hotfix** - Branch para conserto de erros
- **Master** - Branch principal


### Qual a diferença entre criar uma branch local e no servidor?

*Local branch* - Somente você tem acesso às mudanças

*Server branch* - Qualquer pessoa que clonou o projeto tem acesso à essa branch


#### Ok, acho que tá tudo certo, e agora?

### Comandos básicos


Primeiros comandos
        git init

        git add [file.txt]
            (Adicionar somente um arquivo)

        git add .
            (Adicionar tudo)

        git status
            (Verificar o status)

        git rm -r [file.txt]
            (Remover um arquivo específico)

        git commit -m "" 
            (Comentário que ao terminar atualização)


Manipulando as branches

        git checkout -b [Nome da branch] 
            (Cria uma branch e já muda)

        git branch [Nome da branch]
            (Cria a branch)

        git branch -d [Nome da branch]  
            (Deleta a branch)

        git branch -m
            (Renomeia a branch)

        git checkout [Nome da branch]
            (Muda de branch)

Enviando para o servidor

        git push [nome do repositorio] 
            (Envia essa informação para o servidor)

        git push [nome do repositorio] --d [Nome da branch] 
            (Remove uma branch do servidor)

        git clone [url]
            (Clona um repositório)


Criando Tags & Mesclando arquivos

        git tag [nome da Tag]
            (Cria Tags)

        git merge [Nome da branch] 
            (Faz a mescla da sua branch atual com qual você quer)

        git merge [source branch] [target branch] 
            (Faz a mescla entre duas branches)


Outros comandos

        git stash 
            (Salva os arquivos, deixando em um estado "WIP", podendo assim trocar de branch)

        git reset HEAD 
            (Reseta o seu stage (caso não queira enviar ainda))

        git log --oneline
            (Log unificado)

        git diff [source branch] [target branch] 
            (Mostra a diferença de uma branch para outra)

Gerenciando versões remotas

        git remote add [nome do repositorio] [url]
            (Adicionar uma url remota)

        git remote -v 
            (Ver quais remotos você tem)

        git remote rm [nome do repositorio] 
            (Remover uma conexão remota)

        git pull [nome do repositorio] [Nome da branch] 
            (Busca as informações mais atuais)

        git fetch [nome do repositorio] 
            (Sincronizar com o projeto atual)
