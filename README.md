# atividade1-versionamento
Repositório para atividade 1 de Versionamento Senai
fazendo um comentário para o arquivo da atividade 1 de versionamento do Senai;

Passo a passo de comandos pro git e github:
____________________________________________________________________

Antes de tudo, já cria o teu perfil do github e cria um token, salva num .txt na tua desktop porque é uma sequência alfa numérica enorme, já que tu vai 
ser dev e precisa disso pra compartilhar com a sociedade os teus trabalhos!!
Se quiser, já pode criar um repositório remoto por lá, só não te perde nos nomes depois!
____________________________________________________________________

1) criar uma pasta com o nome do repositório - ou trabalho que for fazer
2) criar o novo repositório com o mesmo nome - pra não se perder - no github
3) entra na pasta ainda vazia e clica com o direito, selecionar o "Git Bash Here"
4) inicializar com o comando git init
5) incluir arquivos dentro da pasta que foi criada e com o bash inicializado, pra depois ir salvando no repositório do git
6) rastrear as alterações que foram feitas na pasta com o comando git status
7) deu vermelho? faz um git add . ou git add nome-do-arquivo-criado-que-apareceu-em-vermelho, mas é melhor colocar o add . que sobe tudo já pra staging, dependendo da necessidade
8) e agora dar git status pra verificar se foi pra staging, o nome do(s) arquivo(s) aparecerá agora em verde!
9) dar um "commitar" com o comando git commit -m "comentariozinho pra te lembrar do que está sendo feito"
obs.: não esquece que tu tá na trunk master, se precisar fazer um branch daí só fazer o comando git checkout -b nome-da-branch-nova e pra voltar pra trunk é só 
dar git checkout nome-da-trunk(normalmente master)
10) depois, pode dar um git log só pra ver por onde andas o teu projeto salvo com o commit e as alterações feitas, belezura?
11) também pode dar um git show número-do-commit(sequência alfanumérica) pra ver as alterações ao longo do projeto
12) agora a gente linka os repositórios (local e remoto), pode usar tanto o link do https ou ssh que aparece no git quando tu cria o repositório, coloca 
no bash que tu tá trabalhando o comando git remote add origin endereço-https ou ssh (no caso de exemplo ficaria git remote add origin https://github.com/usuário/nome-do-projeto.git ou git remote add origin git@github.com:usuário/nome-do-projeto.git ))
13) feito isso, meu camaradinha, dá o comando git remote -v (sim, v pra ver mesmo e empurrar pro hub :P)
obs.: vai te aparecer dois links no bash, tu vai fazer o push agora
14) depois é só fazer o comando git push -u origin master
obs.: beleza! foi pra nuvem se tu já tiver logado! Se nãããão, daí vai aparecer uma caixinha pra tu se autenticar.
Coloca na opção de token (lembra daquele que era pra tu salvar num .txt na tua desktop? e faz o teu login). Aparece as confirmações no bash e segue o baile.
15) feito isso, vai no github e dá um F5 no lugar onde tu tava lá com o https ou ssh e vai aparecer a tua publicação
16) dá uma conferida clicando em commits, pra ver o teu trabalho e os movimentos, que equivale a dar o comando git show no bash
____________________________________________________________________
 
Agora, quando tu quiser baixar do remoto pro local e fazer edições, segue abaixo:
____________________________________________________________________

17) pode fazer uma alteração direto no remoto, sem problema nenhum! Vai no projeto ("github/seu-usuário/nome-repositório") 
clica em Add a README (arquivo .md = MarkDown - Lembrar da anistia do tio Mark do facebook)
18) vai aparecer uma telinha onde tu pode escrever o que quiser
19) vai lá em baixo e clica em commit new file
20) vai aparecer uma nova commit na página do projeto com o README criado!!
21) feito isso, baixe pro repositório local essa alteração fazendo no bash o comando git pull
obs.: se tu quiser clonar(copiar) os arquivos do remoto para o local, pode dar um comando git clone https://github.com/usuário/nome do arquivo.git 
pra ter esse link, já sabe, vai no perfil do github do usuário > repositórios > clica no projeto > code > copia o link do projeto 
22) vai aparecer no bash a confirmação com as informações baixadas, ou clonadas, no local

****************************************************************************************************************************

Seguindo num fluxograma, seria mais ou menos assim, até agora:

repositório local ----git add .----> staging area ----git commit----> local.git ----git push----> repositório remoto ----git pull----> repositório local

****************************************************************************************************************************

Se tu quiser ignorar um arquivo e fazer com que ele não seja rastreado pelo git do local:

23) cria um arquivo, dentro de onde tu tá fazendo o projeto, chamado .gitignore
24) arrasta os arquivos que tu quer que sejam ignorados pra dentro desse arquivo .gitignore
25) pra conferir, dá um git status no bash e tu verá somente a criação do .gitignore, mas sem aparecer o(s) arquivo(s) que foram
arrastados pra dentro dessa pasta
26) depois, pode seguir o fluxo com os comandos git add . ; git commit -m "comentário que desejar" e
git push -u origin nome-da-trunk ou branch
____________________________________________________________________

Agora, se tu quiser criar uma branch pra fazer uns trabalhos paralelos:
____________________________________________________________________

27) digita no bash o comando git checkout -b nome-da-branch
28) e pode ir modificando o que quiser (tudo que for modificado - agora - será na nova branch) e fazendo o de sempre nesse
ramo novo, adicionando, "commitando", empurrando, puxando ou clonando do 
remoto para o local
29) depois, se quiser voltar pro trunk dá o comando git checkout nome-da-trunk - ALERTA: não colocar o -b, pois a trunk não será 
criada, estamos apenas retornando para o tronco principal. Se for criar um branch novo, daí sim coloca o -b no comando!!!
30) Se quiser, tu pode juntar, ou MESCLAR, duas branchs. Se tu está em uma das branchs criadas e deseja juntar com outra branch
criada (lembre-se, estamos falando de branchs, não de trunk), usar o comando git merge nome-da-branch-que-quer-juntar-com-a-atual
31) Vai dar uma treta e aparecer conflitos, pois alteramos os mesmos arquivos, porém em branchs diferentes. Então, nesses casos,
devemos apenas informar qual das duas atualizações queremos manter. Então, basta aceitar as duas alterações indo nos arquivos que
foram editados e retirando os conflitos (sinal de igualdade e comparação de maior e menor: >>>, <<<, ===). Deleta esses bugs e salva
os arquivos
____________________________________________________________________

Por fim, vamos fazer o versionamento com tags
____________________________________________________________________

32) fique na trunk ou branch da sua preferência, onde deseja compactar o código com a tag, e digite no bash 
o comando git tag -a vNº -m "comentário" (ex.: git tag -a v1.0 -m "primeira tag")
33) e se quiser ver as tags criadas dá um git tag no bash (se quiser ver em outras branchs ou a trunk, mude para elas com o git checkout)
34) e para ver informações específicas da tag criada dê o comando no bash git show vNº (ex.: git show v1.0)
35) feito isso, empurre para o remoto com git push origin --tags
36) lá no github, atualize a página e clique na tag (menu direito da página) e veja os detalhes e os arquivos compactados nela

Pronto! Agora é exercitar até corroer os dedos. Abraços e até logo!












