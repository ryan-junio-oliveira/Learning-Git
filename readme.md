# 📚 Tutorial Completo de Git --- Principais Comandos

Git é um sistema de controle de versão distribuído, usado para
acompanhar alterações no código e colaborar em projetos.

------------------------------------------------------------------------

## 1️⃣ Configuração inicial

Configure seu nome e email (apenas uma vez por máquina):

``` bash
git config --global user.name "Seu Nome"
git config --global user.email "seu-email@example.com"
```

Ver configurações:

``` bash
git config --list
```

------------------------------------------------------------------------

## 2️⃣ Criar ou clonar repositório

**Novo repositório local:**

``` bash
git init
```

**Clonar repositório existente:**

``` bash
git clone git@github.com:usuario/repositorio.git
```

Ou via HTTPS:

``` bash
git clone https://github.com/usuario/repositorio.git
```

------------------------------------------------------------------------

## 3️⃣ Estado e histórico

Ver estado dos arquivos:

``` bash
git status
```

Ver histórico de commits:

``` bash
git log
```

Resumo compacto:

``` bash
git log --oneline --graph --decorate --all
```

------------------------------------------------------------------------

## 4️⃣ Adicionar e confirmar alterações

Adicionar arquivos específicos:

``` bash
git add arquivo.txt
```

Adicionar tudo:

``` bash
git add .
```

Criar commit:

``` bash
git commit -m "Mensagem do commit"
```

------------------------------------------------------------------------

## 5️⃣ Trabalhando com branches

Criar nova branch:

``` bash
git branch nome-da-branch
```

Trocar de branch:

``` bash
git checkout nome-da-branch
```

Criar e trocar ao mesmo tempo:

``` bash
git checkout -b nome-da-branch
```

Listar branches:

``` bash
git branch
```

------------------------------------------------------------------------

## 6️⃣ Enviar e atualizar código

Enviar branch para o repositório remoto:

``` bash
git push origin nome-da-branch
```

Atualizar branch local com mudanças do remoto:

``` bash
git pull origin nome-da-branch
```

------------------------------------------------------------------------

## 7️⃣ Mesclar alterações

Mesclar outra branch na atual:

``` bash
git merge nome-da-branch
```

Resolver conflitos, depois:

``` bash
git add .
git commit
```

------------------------------------------------------------------------

## 8️⃣ Tags (versões)

Criar tag simples:

``` bash
git tag v1.0.0
```

Criar tag anotada (com descrição):

``` bash
git tag -a v1.0.0 -m "Versão estável 1.0.0"
```

Enviar todas as tags para o remoto:

``` bash
git push origin --tags
```

Excluir tag local:

``` bash
git tag -d v1.0.0
```

Excluir tag remota:

``` bash
git push --delete origin v1.0.0
```

### 🔄 Atualizar (mover) uma tag existente para outro commit

As tags não se movem automaticamente. Para "reapontar" uma tag existente
(por exemplo `v0.0.6`) para um novo commit:

``` bash
# 1. Apagar a tag local
git tag -d v0.0.6

# 2. (Opcional) Apagar a tag remota antiga
git push origin :refs/tags/v0.0.6

# 3. Criar novamente a tag no commit atual (ex.: HEAD da main)
git tag -a v0.0.6 -m "Release v0.0.6 atualizado"

# 4. Enviar forçando a atualização no GitHub
git push origin v0.0.6 --force
```

⚠️ **Boas práticas:** para não confundir quem já baixou, é mais seguro
criar uma nova tag (`v0.0.7`) em vez de reusar a antiga.

------------------------------------------------------------------------

## 9️⃣ Desfazer alterações

Remover arquivos do staging:

``` bash
git reset arquivo.txt
```

Reverter commit mantendo alterações:

``` bash
git reset --soft HEAD~1
```

Reverter commit descartando alterações:

``` bash
git reset --hard HEAD~1
```

Reverter commit sem alterar histórico:

``` bash
git revert <hash-do-commit>
```

------------------------------------------------------------------------

## 🔟 Limpeza de arquivos

Remover arquivo do Git mas manter local:

``` bash
git rm --cached arquivo.txt
```

Ignorar arquivos:

``` bash
echo "arquivo.log" >> .gitignore
```

------------------------------------------------------------------------

## 1️⃣1️⃣ Git LFS (arquivos grandes)

Instalar e configurar:

``` bash
git lfs install
git lfs track "*.exe"
git add .gitattributes
```

Adicionar e enviar:

``` bash
git add arquivo.exe
git commit -m "Adiciona arquivo grande"
git push origin branch
```

------------------------------------------------------------------------

## 1️⃣2️⃣ Comandos úteis

Ver diferenças:

``` bash
git diff
```

Sincronizar branch local com o remoto:

``` bash
git fetch origin
git merge origin/main
```

Remover branch local:

``` bash
git branch -d nome-da-branch
```

Remover branch remota:

``` bash
git push origin --delete nome-da-branch
```

------------------------------------------------------------------------

## 1️⃣3️⃣ Gerar chave SSH e adicionar ao GitHub

*(mantém o conteúdo que você já tinha aqui...)*

------------------------------------------------------------------------

📌 **Dica final:** use sempre `git status` para saber onde você está e
`git log --oneline --graph` para entender o histórico.
