# Comandos GIT

### Configurações Iniciais GIT
git config --global color.uit true  
git config --global user.name "Nome Sobrenome"  
git config --global user.email seuemail@provedor.com.br

### Verificando configurações
git config --list  

### Criando um repositório
Navegar até a pasta do projeto  
git init  

### Fluxo de commits 
git add .  $ git commit -m "Mensagem
ou 
git commit -a -m "Descrição Commit"

### Verificando todos os hashs de commit 
git log

Verificando todos os commits e alterações
git log -p 

### Verificando as estaticas das mudanças
git log -stat
git log --pretty=oneline
git log --pretty=format:"%h - %an, %ar : %s" (%h hash, %an usuário, %ar tempo, %s descrição do commit)

### Commits a x days atras
git log --since=2.days

### Ignorando arquivos no git
touch .gitignore edite o arquivo, colocando em cada linha a pasta ou arquivo a ser ignorado, o arquivo .gitignore deve ser commitado, pois 
o git faz controle de seus proprios arquivos

### Resolvendo problemas de .gitignore
git rm -r --cached .   
git add .  
git commit -am "Remove ignored files"  

### Voltando o arquivo para versão anterior untracked files
git reset HEAD nome ou caminho do arquivo

### Fluxo de Commits
git checkout hash (hash do commit)  
git reset HEAD~1 --soft Exclui o ultimo commit e volta o arquivo para ser novamente comitado    
git reset HEAD~1 --hard Exclui o commit, os arquivos e as suas alterações    

### Branchs
git branch nomedobranch (Criar um novo branch)  
git checkout -b nomedobranch  (Criar um novo branch, apartir do branch atual)  
git branch -d nomedobranch (Deletar um branch)
git checkout branch (Acessa o branch)  

### Versionamento Semantico
Forma organizada de gerar versões do software  
x.x.x - Major, Minor, Patch  
Major alterada pode quebrar TOTALMENTE a compatibilidade exemplo 1.0.1 para 2.0.0  
Minor alterada pode quebrar a compatibilidade, mas mantém não pode quebrar totalmente, deve ser ter um minimo de compatibilidade com 
a versão MAJOR exemplo 1.1.2 para 1.2.0  
Patch SEMPRE Mantém Compatibilidade, 1.1.1 para 1.1.2, 1.1.3  

Regra de Ouro  
Mudou apenas patch, atualize sem maiores cuidados  
Mudou minor, faça os testes e leia a documentação para verificar a compatibilidade  
Mudou Major, cuidado, refazer seu software, pode ser algo trabalhoso, mudança em tudo, estrutura, novas formas de escrita de uma funcionalidade  

Mudanças de Patch devem manter a compatibilidade, exemplo 0.0.Patch, 0.0.1 para 0.0.2, deve ser respeitada a compatibilidade
Exemplo major version alterada, exemplo 1.0.0 para 2.0.0, compatibilidade não precisa ser mantida

Version 1 - Versão Principal
Version 1.1.8 Versão Principal com compatibilidade mantida
Version 1.2.1 Pode quebrar a compatibilidade, mas não pode quebrar de forma geral
Version 2.0 Pode quebrar totalmente a compatibilidade

### Visualizando repositorios locais e remotos
git branch -a

### Removendo uma tag remota
git push --delete origin tagname

### Removendo uma tag local
git tag --delete tagname
