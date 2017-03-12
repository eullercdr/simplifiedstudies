# Estrutura de pastas linux

/home = pasta de usuarios
/dev = devices
/media = driver de cd
/root = estrutura de pasta do root/superusuario
/tmp = logs etc
/etc=arquivos de configuracao
/var=conteudo de arquivos logs, mysql
/bin=executavel
/user/bin=executaveis
/lib=bibliotecas

# Comandos Básicos

mkdir = criar diretorio
touch = criar arquivo
ls -l = ver tipos de arquivo
touch .qualquernome = criação de arquivo oculto
ls -la = lista todos os arquivos, até ocultos
rm = remover arquivo 
rm arquivo = remove um unico arquivo
rm -rf diretorio = remover um diretorio
rm -rf * = remove tudo dentro de um contexto
mv arquivo nomenovo = renomear arquivo
sudo chown euller diretorio= muda o dono do arquivo
find . -name arquivo = buscar um arquivo
find . -name "oi*" = buscar um arquivo
ls -la | grep oi = busca arquivos com um filtro
ln -s framework framework2 = cria um link simbolico de framework pra framework2
cat arquivo = exibe o conteudo de uma arquivo
top = tempo real de tudo que está acontecendo na máquina
whoami = mostra o usuário logado
d=diretorio , a = arquivo, s=socket

# Permissões de Arquivo

USUARIO  |GRUPO  | OUTROS (USUARIO ANONIMO)
rwx        rwx     rwx
r=read w=write x=execute

# Permissões CHMOD

chmod u+x arquivo.txt - Adicionar permissão de usuario para executar
chmod g+r arquivo.txt - Adicionar permissão de leitura para o grupo
chmod g=rwx arquivo.txt
Para retirar uma permissão basta usar o comando - (menos)

Permissão |  Binário | Decimal
---           000         0
--x           001         1
-w-           010         2
-wx           011         3
r--           100         4
r-x           101         5
rw-           110         6
rwx           111         7 
                          
chmod 644 = UGO
chmod -R 777 = Todos os arquivos e subpastas terão a permissão

Mudar o dono de um arquivo

Cuidado com 777 - Ultimo 7, deixa até o usuário anonimo ler executar e escrever no arquivo (MUITO SÉRIO)
