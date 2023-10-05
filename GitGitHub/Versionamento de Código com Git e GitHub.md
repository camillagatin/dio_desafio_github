# Versionamento de Código com Git e GitHub

## **Git**

### Sistemas de Controle de Versão

**Controlam as versões de um arquivo ao longo do tempo.**

- Registra o histórico de atualizações de um arquivo;
- Gerencia quais foram as alterações, a data, autor, etc.;
- Organização, controle e segurança.

---

### Tipos de Sistemas de Controle de Versão

**Dentre os Sistemas de Controle de Versão (VCS), temos:**

- VCS Centralizado (CVCS)
    - Exemplo: CVS, Subversion

<img src="/GitGitHub/images/Untitled.png">

- VCS Distribuído (DVCS)
    - Exemplo: Git, Mercurial

<img src="/GitGitHub/images/Untitled 1.png">

---

### VCS Distribuído (DVCS)

**Clona o repositório** **completo, o que inclui o histórico de versões.**

- Cada clone é como um backup;
- Possibilita um fluxo de trabalho flexível;
- Possibilidade de trabalhar sem conexão à rede.

---

### O que é GIT

**Sistema de Controle de Versão Distribuído.**

- Gratuito e Open Source (Código Aberto);
- Ramificações (branching) e fusões (merging) eficientes;
- Leve e rápido.

---

# ▼ Download do Git ▼

[Git - Downloading Package](https://git-scm.com/download/win)

[Git - Documentation](https://git-scm.com/doc)

---

## **GitHub**

### O que é GitHub

**Plataforma de hospedagem de código para controle de versão com Git, e colaboração.**

- Comunidade ativa;
- Utilizado mundialmente;
- Mascote “Octocat”.
<img src="/GitGitHub/images/Untitled 2.png">

---

### Configurando o Git

<img src="/GitGitHub/images/Untitled 3.png">

```
git config
CTRL + L (limpar terminal)
git config --global user.name "nome-sobrenome"
git config --global user.email seu-email@email.com
git config init.defaultBranch
(seta pra cima copia o código de cima) git config --global init.defaultBranch main
```

---

### Versionamento/Autenticando com Token e SSH

```
git clone https://github.com/user-name/hello-world.git
user-name
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 (token gerado no github)
git config --global credential.helper store (salvar o repositório permanentemente para não precisar ficar gerando tokens)
git clone https://github.com/user-name/hello-world.git
user-name
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 (token gerado no github)
(apagar a pasta "hello-world") git clone https://github.com/user-name/hello-world.git
```

---

### Criando e Clonando Repositórios

```
mkdir repo-local
cd repo-local/
git init
cd .git
git clone https://github.com/user-name/hello-world.git repo-clonado
cd repo-clonado
cd .git
cat config
cd ..
git remote add origin (endereço do repositório)
```

---

### Salvando Alterações no Repositório local

```
mkdir dio-resumos-git-e-github
cd dio-resumos-git-e-github/
git init 
git status
touch README.md
git status
```

- Site para criar README de forma simples
[readme.so](https://readme.so/pt)


```
git add README.md
git status
git commit -m"commit inicial"
git log
clear
git status
mkdir resumos
touch resumos/resumos aula1.md
git status
echo resumos/ > .gitignore
git status
echo > .gitignore
git status
```

---

### Desfazendo Alterações no Repositório local

```
git init (se fosse sem querer)
rm -rf.git
git status
(se apagar o conteúdo do README sem querer)
git restore README.md
git log
git commit --amend -m"adiciona gitignore e diretórios aulas e resumos"
git log
(desfazer o commit)
git reset --soft (copiar endereço do commit)
```

---

### Enviando e Baixando Alterações com o Repositório Remoto

criar um novo repositório sem README: dio-resumos-git-e-github

```
git status
git remote add origin (colar url)
git push -u origin main
(fazer alterações pelo github)
git pull (puxar e mesclar as alterações feitas no github)
```

---

### Trabalhando com Branches

**De maneira simplista, uma Branch (em tradução, “Ramo”), é uma ramificação do seu projeto.**

- É um ponteiro móvel para um commit no histórico do repositório;
- Quando você cria uma nova Branch a partir de outra existente, a nova se inicia apontando para o mesmo commit da Branch que estava quando foi criada.

```
git checkout -b teste
echo "#commit-3-branch-teste" > commit-3-teste.txt
git add .
git commit -m"commit-3"
git log
git checkout main
clear
git branch -v
git merge teste
git branch -d teste
git branch
```