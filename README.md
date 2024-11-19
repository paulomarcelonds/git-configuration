# Introdução - Configuração Inicial do Git

## Configuração do Git pela Primeira Vez

Agora que você tem o Git instalado no seu sistema, é importante personalizar seu ambiente para facilitar seu uso. Essas configurações iniciais geralmente precisam ser feitas apenas uma vez por computador, mas podem ser ajustadas posteriormente, se necessário, executando os mesmos comandos.

O Git utiliza uma ferramenta chamada `git config` para gerenciar variáveis de configuração que controlam como ele opera. Essas configurações podem ser armazenadas em três níveis diferentes:

### Níveis de Configuração do Git

1. **[path]/etc/gitconfigfile**  
   - Contém valores aplicados a todos os usuários no sistema e a todos os repositórios.  
   - Use a opção `--system` com o comando `git config` para acessar ou modificar este arquivo.  
   - Alterações nesse arquivo exigem privilégios administrativos.

2. **~/.gitconfig ou ~/.config/git/config**  
   - Armazena valores específicos para o usuário atual.  
   - Use a opção `--global` para definir configurações globais que afetam todos os repositórios do usuário no sistema.

3. **.git/config no diretório de um repositório Git**  
   - Configurações específicas para um único repositório.  
   - Use a opção `--local` para definir configurações locais, ou omita opções para que este seja o comportamento padrão.  
   - Este arquivo só é acessível quando você está dentro de um repositório Git.

### Precedência das Configurações

- Configurações em `.git/config` têm prioridade sobre as do `~/.gitconfig`, que, por sua vez, prevalecem sobre as do `[path]/etc/gitconfig`.

### Configuração em Sistemas Windows

- No Windows, o Git procura o arquivo `.gitconfig` no diretório `$HOME` (geralmente `C:\Users\$USER`).  
- O arquivo `[path]/etc/gitconfig` está localizado na raiz do MSys, correspondente ao local onde o Git foi instalado.  
- A partir da versão 2.x do Git para Windows, também há um arquivo de configuração de nível de sistema:
  - **Windows XP:** `C:\Documents and Settings\All Users\Application Data\Git\config`
  - **Windows Vista e superiores:** `C:\ProgramData\Git\config`

Para alterar esse arquivo de configuração, você deve usar o comando:  

```bash
git config -f <file> 
```

## Visualizando Configurações
Para listar todas as configurações e seus arquivos de origem, execute:

```bash
git config --list --show-origin
```

## Configurando seu usuario e e-mail
A primeira configuração ao instalar o Git é definir seu nome de usuário e endereço de e-mail. Essas informações são incorporadas a cada commit que você criar.

Para definir seu usuário e email globalmente, execute:

```bash
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
```

- A opção `--global` garante que essas configurações sejam aplicadas a todos os repositórios no sistema.
- Para projetos específicos, você pode definir um nome e e-mail diferentes omitindo a opção `--global` e executando o comando dentro do diretório do repositório.
