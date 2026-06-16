# Guia rapido de Git para iniciantes

Este guia reune os principais comandos de Git para um profissional que esta comecando a trabalhar com versionamento de codigo.

## O que e Git?

Git e uma ferramenta de controle de versao. Ele permite acompanhar alteracoes em arquivos, voltar para versoes anteriores, trabalhar em equipe e manter o historico do projeto organizado.

## Configuracao inicial

Antes de usar o Git pela primeira vez, configure seu nome e e-mail:

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seu.email@exemplo.com"
```

Para conferir as configuracoes:

```bash
git config --list
```

## Criar ou clonar um repositorio

Criar um repositorio Git em uma pasta existente:

```bash
git init
```

Clonar um repositorio remoto:

```bash
git clone https://github.com/usuario/repositorio.git
```

Entrar na pasta do projeto:

```bash
cd nome-do-repositorio
```

## Verificar o estado do projeto

Mostra arquivos modificados, novos arquivos e o que esta pronto para commit:

```bash
git status
```

Este e um dos comandos mais usados no dia a dia.

## Adicionar arquivos para commit

Adicionar um arquivo especifico:

```bash
git add arquivo.txt
```

Adicionar todos os arquivos alterados:

```bash
git add .
```

## Criar um commit

Commit registra uma versao do projeto no historico:

```bash
git commit -m "Mensagem explicando a alteracao"
```

Boas mensagens de commit devem ser curtas e claras, por exemplo:

```bash
git commit -m "Adiciona README inicial"
```

## Ver historico de commits

Visualizar o historico completo:

```bash
git log
```

Visualizar historico resumido:

```bash
git log --oneline
```

## Enviar alteracoes para o repositorio remoto

Enviar commits locais para o GitHub ou outro servidor remoto:

```bash
git push
```

Na primeira vez em uma branch nova, pode ser necessario usar:

```bash
git push -u origin nome-da-branch
```

## Baixar alteracoes do repositorio remoto

Baixar e aplicar alteracoes remotas:

```bash
git pull
```

Buscar informacoes do remoto sem aplicar automaticamente:

```bash
git fetch
```

## Trabalhar com branches

Branch e uma linha de trabalho separada. Ela permite desenvolver funcionalidades sem alterar diretamente a branch principal.

Listar branches:

```bash
git branch
```

Criar uma nova branch:

```bash
git branch nome-da-branch
```

Entrar em uma branch:

```bash
git checkout nome-da-branch
```

Criar e entrar em uma branch ao mesmo tempo:

```bash
git checkout -b nome-da-branch
```

Em versoes mais novas do Git, tambem e possivel usar:

```bash
git switch nome-da-branch
git switch -c nome-da-branch
```

## Juntar alteracoes de outra branch

Para trazer alteracoes de uma branch para a branch atual:

```bash
git merge nome-da-branch
```

Exemplo comum:

```bash
git checkout main
git merge minha-feature
```

## Ver diferencas nos arquivos

Ver alteracoes ainda nao adicionadas:

```bash
git diff
```

Ver alteracoes que ja foram adicionadas com `git add`:

```bash
git diff --staged
```

## Desfazer alteracoes

Desfazer alteracao em um arquivo antes do `git add`:

```bash
git restore arquivo.txt
```

Remover arquivo da area de stage, mantendo a alteracao no arquivo:

```bash
git restore --staged arquivo.txt
```

Reverter um commit criando um novo commit de correcao:

```bash
git revert codigo-do-commit
```

Use comandos como `reset --hard` com muito cuidado, pois podem apagar alteracoes locais.

## Trabalhar com repositorio remoto

Listar remotos configurados:

```bash
git remote -v
```

Adicionar um remoto:

```bash
git remote add origin https://github.com/usuario/repositorio.git
```

Alterar a URL do remoto:

```bash
git remote set-url origin https://github.com/usuario/novo-repositorio.git
```

## Fluxo basico recomendado

Um fluxo simples de trabalho com Git:

```bash
git status
git pull
git checkout -b minha-alteracao
git add .
git commit -m "Descreve a alteracao feita"
git push -u origin minha-alteracao
```

Depois disso, normalmente voce abre um Pull Request no GitHub para revisar e juntar a alteracao na branch principal.

## Comandos mais usados

```bash
git status
git add .
git commit -m "Mensagem"
git pull
git push
git branch
git checkout -b nome-da-branch
git log --oneline
git diff
```

## Boas praticas

- Execute `git status` com frequencia.
- Faca commits pequenos e objetivos.
- Escreva mensagens de commit claras.
- Atualize sua branch com `git pull` antes de iniciar novas alteracoes.
- Use branches para cada funcionalidade ou correcao.
- Evite enviar arquivos desnecessarios, como dependencias, arquivos temporarios e senhas.
- Nunca publique senhas, tokens ou chaves de acesso no repositorio.

## Glossario rapido

- Repositorio: pasta controlada pelo Git.
- Commit: registro de uma alteracao no historico.
- Branch: linha separada de desenvolvimento.
- Merge: uniao de alteracoes de uma branch em outra.
- Remote: repositorio hospedado fora da maquina local, como no GitHub.
- Push: envio de commits locais para o remoto.
- Pull: busca e aplicacao de alteracoes do remoto.
- Stage: area onde arquivos ficam preparados para commit.

