# Configuração e Uso do Git e GitHub

## Instalação e Configuração Inicial

### Instalar o Git no Computador Local
1. Baixe e instale o Git a partir do [site oficial](https://git-scm.com/).
2. Adicione o Git ao PATH do Windows durante a instalação ou manualmente.

### Configurando o Git
No terminal, configure seu e-mail e nome de usuário:
```sh
git config --global user.email "seuemail@exemplo.com"
git config --global user.name "Seu Nome"
```

### Configurando a Chave SSH
1. Gere uma chave SSH:
    ```sh
    ssh-keygen -t ed25519 -C "seuemail@exemplo.com"
    ```
2. Adicione a chave SSH ao GitHub:
    - Vá para **Settings** -> **SSH and GPG keys** no GitHub.
    - Cole a chave pública gerada.

## Criando e Configurando um Repositório

### Passo 1: Criar Repositório no GitHub
Crie um novo repositório no GitHub pelo site.

### Passo 2: Configurar Repositório Localmente
#### Caso já tenha o repositório
```sh
git remote add origin LINK_DO_REPOSITÓRIO
git branch -M master
git push -u origin master
```

#### Caso ainda não tenha adicionado no repositório
```sh
echo "#nome-do-projeto" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M master
git remote add origin https://github.com/seuusuario/nome-do-projeto.git
git push -u origin master
```

## Clonando um Repositório
Para clonar um repositório, utilize:
```sh
git clone URL_DO_REPOSITÓRIO
```

## Comandos Úteis do Git

### Status e Histórico
- `git status`: Mostra alterações e quais arquivos precisam ser adicionados.
- `git log`: Exibe os commits feitos no projeto e quem os realizou.
- `git remote`: Lista os repositórios remotos configurados.

### Atualização e Reversão
- `git pull origin main`: Baixa os commits do repositório remoto para o local.
- `git revert ID_DO_COMMIT`: Desfaz um commit específico.
- `git reset --hard ID_DO_COMMIT_ANTERIOR`: Apaga o commit e retorna o código ao estado anterior. **Nota**: Não apague commits que foram enviados ao repositório remoto.

### Alteração de Commit
- `git commit --amend -m "nova mensagem"`: Altera a mensagem do último commit.

## Arquivo .gitignore
Crie um arquivo `.gitignore` com as regras para ignorar arquivos indesejados. Utilize [gitignore.io](https://www.toptal.com/developers/gitignore) para gerar um template adequado ao seu projeto.

## Lidando com Conflitos
Ao ocorrer um conflito de merge, escolha as alterações corretas, apague as erradas e refaça o commit.

## Controle de Acesso
Os repositórios públicos são apenas para leitura. Somente o dono pode adicionar colaboradores.

## Estados dos Arquivos no Git
- **M (Modified)**: Arquivo modificado que ainda não foi registrado.
- **U (Untracked)**: Arquivo novo que ainda não foi adicionado ao controle de versão.

## Boas Práticas para Mensagens de Commit
- **Curta e Concisa**: A primeira linha deve ter no máximo 72 caracteres. Adicione detalhes adicionais em linhas subsequentes.
- **Verbo no Infinitivo**: Use verbos como "adicionar", "corrigir", "atualizar".
- **Evite Detalhes Técnicos**: Detalhes complexos devem estar nos comentários do código ou na documentação.
