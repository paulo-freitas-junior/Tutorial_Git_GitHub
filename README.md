# Tutorial Git/Github
## Procedimentos para armazenamento e versionamento de arquivos
---
Este tutorial tem a função de ser um guia simples dos principais comandos a serem usados do <b>git</b> no <b>github</b>.

Para tal, espera-se que você já possua uma conta cadastrada no Github, www.github.com

Os procedimentos a seguir tem por objetivo o aprendizado utilizando terminal de acesso GitBash (linha de comando).

### Inicializando os diretórios de trabalho

<b>Diretório Local no computador</b>  
Pasta local do computador, abrir o GitBash e executar o comando <b>git init</b>

<b>GitHub</b>
1º Passo - Entrar em 'Repositóries' e criar um novo repositório
2º Passo - Copiar o Link do Repositório criado  
3º Passo - Executar o comando para configurar o acesso remoto ao repositório criado:

<b><center>git remote add origin</b> [link do repositório]</center>


---
### Comandos básicos do Git
1. <b>Criar pasta de trabalho (repositório) local:</b>

    Usando <b>Gitbash</b>, executar os comandos na pasta local:

       git init - inicializa o repositório.
       git status - Verifica a Branch de trabalho e o status dos arquivos.
       git add "nome do arquivo" - Adiciona arquivos para o "track" e posteriormente para serem feitos os "commits".
       git add - Adiciona todos os arquivos (vermelhos) para o controle de versão.
       git commit -m "versão1, versão 2, etc" - Comando que cria a vesão do arquivo com mensagem especificando as alterações.
       git push - Comando para enviar os arquivos prontos e versionados para o GitHub.

2.  <b>Gerando nova versão dos arquivos já criados:</b>

    Depois de alterados os arquivos na pasta <b>local</b> seguir os passos:

        git add. - Adicionar os arquivos para versão.
        git status - Verificar se os arquivos estão prontos.
        git commit -m "Mensagem" - Novas linhas e versão inseridas.
        git push - Enviar os arquivos para o GitHub.
        git reflog - Verifica o log das versões que foram adicionadas.


3. <b>Como voltar a uma versão anterior.</b>

    Pasta Local:
  
       git add. - Adicionar os arquivos para versão.
       git status - Verificar se os arquivos estão prontos.
       git commit -m "Mensagem" - Novas linhas e versão inseridas.
       git push - Enviar os arquivos para o GitHub.
       git reflog - Verifica o log das versões que foram adicionadas.

4. <b>Branch</b>
    São locais ou "Pastas" para o armazenamento das verões dos arquivos definidas por:

    - <b>Principal "Master" ou "Main"</b> -  Onde são alocadas as versões funcionais dos arquivos, geralmente em ambiente de produção.
    - <b>Staging</b> - Ambiente de trabalho das versões dos arquivos em alteração para serem validados.

          git branch - Verifica quais Branchs estão disponíveis no momento.
          git branch staging - cria uma branch com o nome 'staging'.
          git checkout staging - Altera o ambiente de trabalho para a nova branch criada (staging).

<center>Todos as alterações alterações nos arquivos à partir desse ponto serão direcionados para a <b>branch staging</b> que foi criada e definida como novo ambiente de trabalho.</center>

<p></p>

       Passos após alteração dos arquivos:
       1º Passo: git status
       2º Passo: git add.
       3º Passo: git commit -m "mensagem de nova branch"
       4º Passo: git status
       5º Passo: git push

5.  <b>Merge</b>
Função merge serve paa unir os arquivos de uma Branch para outra.

        git branch - verifica se está na branch com os arquivos atualizados
        git checkout master - Entra na branch Master que é a branch onde se deseja atualizar os arquivos.
        git branch - Verifica novamente se está na branch Master
        git pull - Faz o download dos arquivos ATUALIZADOS que estão no GITHUB para a maquina local.
        git merge 'staging' - Puxa os arquivos da branch selecionada "staging" para a branch atual "Master".
        git push - Envia os arquivos para o GitHub.

6. <b>Trabalhando em Equipe ou com Diversas Branchs</b>
Passos para se densenvolver um trabalho com equipe ou diversas branchs.

    1º - <b>git pull</b> da branch principal "master"
    2º - <b>gerar uma nova branch</b> a partir da princial "master"
    3º - <b>trabalhar os arquivos</b> na branch criada
    4º - <b>finalizar o trabalho</b> na branch criada
    5º - <b>git checkout</b> na branch principal "master"
    6º - <b>git pull</b> pegar os arquivos atualizados do GitHub
    7º - <b>merge</b> branch temporária com a branch principal "master"
    8º - <b>git push</b> da branch principal

<p></p>

7. <b>Executando o processo acima via comandos:</b>

       git checkout master
       git checkout -b [nome nova branch] master
       git branch

       "cria-se os arquivos de trabalho"

       git add.
       git status
       git commit -m "Mensagem"
       git chekout master
       git pull
       git merge [nome da branch onde SE ESTA TRABALHANDO]
       git push

8.  <b> Pull Request</b>
É o processo de validação dos arquivos.

" FAZER UMA REVISÃO DESSA PARTE" E INSERIR NO ARQUIVO!!!!!!!!!!!

9.  <b>Git Ignore</b>
Usado para não permitir que os controle de versão Git enviem arquivos ou pastas.

    1º Passo - <b>Estar na pasta principal</b> logo após de CRIADA!
    -   Será criado um arquivo chamado (.)
    -   Abrir o arquivo com notepad
    -   Inserir o nome dos arquivos a serem ignorados
    -   Inserir o nome das pastas com barra no final ( ignorados/ )

    2º Passo - <b>git status</b>
    3º Passo - <b>git add.</b>
    4º Passo - <b>git status</b>
    5º Passo - <b>git commit -m "add arquivo gitignore"</b>
    6º Passo - <b>git push</b>

<p></p>

10. <b>Clonando Repositórios</b>
Clonar repositórios é conhecido como "FORK" onde você clona um reposítório de outra pessoa e pode personalizar os arquivos conforme a sua necessidade ou como forma de ajudar o processo de criação e depois informar o dono do repositório sobre as alterações. Caso seja de interesse ele pode permitir a alteração no repositório original.

<p></p>

    1º Passo - Criar uma pasta LOCAL para o repositório a ser clonado.
    2º Passo - Executar o comando do git clone:

        git clone [endereço HTTPS do repositório]


11. <b> Demais comandos do GIT</b>
Comandos diversos:

    <b>git diff</b> - Mostra as alterações que foram efetuadas nos arquivos originais/alterados que **não** foram para área de **staged** através do comando **git add.**.
    <b>git diff --staged</b> - Mesma função do DIFF, porém para os arquivos que foram para <b>staged area</b>.
    <b>git restore [arquivo]</b> - Restaura para a atualiação original, o arquivo que foi atualizado e que <b>não foi adicionado</b> na staged area.
    <b>git restpre --staged[nome do arquivo]</b> - Restaura o arquivo que foi <b>adicionado</b> na staged area com a flag para <b>modificado</b>.
    