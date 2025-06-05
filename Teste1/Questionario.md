QUESTIONARIO

Cite 6 fatores do Twelve-Factor App e explique cada um deles.
Resposta:
1-Base de Codigo
Cada aplica��o possui seu pr�prio rep�sitorio e se pode ter v�rias intancias dele.

2-Depend�ncias
Deve-se declarar todas as depend�ncias de forma explicita,
utilizando principalmente a ferramenta Nuget (no contexto .net) para que fiquem vis�vel no arquivo .csproj 
e tambem na biblioteca Nuget.

3-Configura��es
Configura��es como CS, variaveis de ambiente ou dados sens�veis devem ficar fora do codigo,
se preciso em variaveis de ambiente para ser gerenciada em CI/CD.

4- Servi�os de Apoio
Quaisquer servi�os externos (como banco de dados) tem que ser tratado como um recurso que pode ser alterado facilmente,
no caso de banco de dados por exemplo, nada de CS em harded coded,
para que possa ser alterada facilmente dependendo do ambiente (com variaveis).

5-Build, Release e Run
Separar o processo nessas 3 etapas para evitar que mudan�as no codigo possa quebrar algum ambiente em caso de deploy.
Em .net isso pode ser realizado com dotnet build e dotnet run por exemplo.

6-Concorr�ncia
Use ferramentas como docker e kubernets para escalar o processo,
o .net utiliza o Kestrel para lidar com multiplas threads mas dependendo do nivel de requisi��es
e usu�rios ativos pode ser necess�rio escalar horizontalmente com alguma das ferramentas citadas.

Quais s�o as principais camadas no desenvolvimento de um software?
Resposta:
As principais camadas (se tratando de arquiiteturas populares como clean e screaming architeture) s�o:
Camada de apresenta��o:
� a primeira camada da aplica��o no sentido de fora para dentro, onde a requisi��o externa chega,
geralmente se apresenta em classes de 'Controller'.
Camada de aplica��o:
� o local onde define o 'core' do projeto, as regras de neg�cios e a parte l�gica do processo,
geralmente se apresentando em classes de 'Services'.
Camada de Dominio:
� a camada que define os modelos e entidades da aplica��o,
geralmente � possui dados que ser�o consumidos pelas outras camadas.

Diferencie Arquitetura SOA X Arquitetura microservi�os.
Resposta:
Microservi�os geralmente s�o mais independentes, geralmente com maior separa��o e apartando contextos ainda menores,
geralmente utilizam docker e kubernetes com mais frequencia.
SOA � uma separa��o interna dentro de uma mesma aplica��o, 
onde � apartado a funcionalidade e responsabilidade de cada 'assunto' em servi�os independentes que se comunicam entre si.

Qual � o objetivo de um API Management na arquitetura de servi�os distribu�dos? Cite vantagens e desvantagens.
Resposta:
API Management � basicamente a parte que faz a intermedia��o entre dados externos (clientes, aplica��es,
outros tipos de requisi��es) e a propria aplica��o.
As principais vantangens podemos citar como:
Gerenciamento centralizado, todas os endpoints s�o centralizados, podendo configurar politicas de acesso,
rate limite, caching, auth entre outras configs de forma geral para todos endpoints.
Facilidade tambem pode ser considerado uma vantagem, haja vista que existe bibliotecas
e ferramentas que facilitam a utiliza��o como swagger/openApi e � comumente utilizado.

Como desvantagens podemos citar:
A depend�ncia de outras ferramentas, como Azure Api Management ou at� mesmo o swagger como citado anteriormente.
Outra desvantagem que pode ser considerada � o nivel de 'complexidade' adcional a sua aplica��o,
tendo que vista que n�o � algo realmente obrig�torio, ent�o � bom ser feito uma an�lise para avaliar se vale a utiliza��o.

Qual a diferen�a entre uma Struct e uma Class?
Resposta:
Dentre as principais diferen�as podemos citar a Heran�a, que � comumente utilizado em classes e o struct n�o suporta,
o tipo de armazenamento em mem�ria e o impacto que isso pode ter em alguns contextos, como em collections.

Explique a grande diferen�a entre .NET e .NET CORE.
Resposta:
A principal diferen�a � no aspecto 'plataforma' o .net � exclusivo para windows, 
o .net core � multiplataforma, podendo rodar em qualquer sistema operacional.

Quais as principais diferen�as entre REST e GRPC?
Resposta:
REST � o padr�o de comunica��o mais utilizado no mundo, tem metodos bem claros e de nome auto-explicativo, 
j� o GRPC � extramemente �til para comunica��o entre sistemas por se tratar de uma comunica��o bin�ria direta 
por�m exige um nivel de conhecimento t�cnico mais elevado 
e adciona um patamar de complexidade na aplica��o que tem que ser levado em conta.

Explique como funciona um gerenciamento de rotas de uma SPA.
Resposta:
� realizado de forma flu�da com defini��o de Rota/Roteador, navega��o do cliente e carregamento de dados. 
Quando � acessado uma URL o roteador intercepta a requisi��o e decide qual componente exibir,
carregando somente os dados necess�rios.

Falando sobre DevOps, comente o que conhece sobre.
Resposta:
Conhe�o as principais etapas de CI/CD que � executadada durante uma pipeline antecedendo o deploy em ambiente.
Alem disso as partes referente gerenciamento e monitoramento de memoria, 
status e escalabilidade de pods atrav�s de docker e kubernets.

Explique sobre um m�todo agile.
Resposta:
SCRUM, se trata da forma do qual uma equipe ir� gerenciar suas demandas,
contando geralmente com 'sprints' de 2 semanas (podendo ser maior dependendo da complexidade do projeto), 
cerim�nias di�rias (dailys), cerim�nias de novos projetos (Refinamentos) entre outras como Review e Retro.

Comente sobre CI e CD e algumas ferramentas do dia a dia.
Resposta:
CI se trata das etapas referente ao proprio projeto,
nesta etapa podem ser configuradas: execu��o de build, testes da aplica��o, 
utiliza��o de alguma ferramenta de monitoramento como sonarqube.
CD se trata das etapas referente ao pr�prio ambiente, 
nela geralmente � carregada as vari�veis que ser�o utilizadas em cada ambiente
e tamb�m a geralmente ultima e mais importante etapa, que � o Deploy da aplica��o.

Qual a diferen�a entre Docker e Containers.
Resposta:
Docker � a ferramenta do qual conseguimos criar pequenos 'ecosistemas' onde podemos gerenciar
praticamente qualquer software, Container � o nome dado ao 'espa�o' reservado que podemos criar
e escalar dentro do docker.

Qual a diferen�a entre Kubernetes e Openshift?
Resposta:
Kubernets � o mais popular orquestrador de containers, � um servi�o open-source do google. 
OpenShift seria um concorrente do kubernets da plataforma RedHat.

Quais as vantagens e desvantagens sobre API e quais preocupa��es devemos ter quando escolhemos essa abordagem?
Resposta:
Escalabilidade, reutiliza��o, facil integra��o com sistemas e flexbilidade para SPAs modernos.
Preucupa��o pode ser citada a seguran�a e o desempenho (lat�ncia).

Como conseguimos garantir um n�vel de seguran�a satisfat�rio no uso de APIS?
Resposta:
A forma mais conhecida e popular � a utiliza��o de JWT para autoriza��o ao acessar os servi�os

Para que serve uma arquitetura de mensagerias?
Resposta:
Mensagerias possuem muitas vantagens, mas as principais podemos citar a escalabilidade, 
a facil integra��o com ferramentas pr�prias e o desacoplamento da propria aplica��o.

Explique a estrat�gia SAGA em arquitetura de microservice.
Resposta:
A estrat�gia Saga em microservi�os � um padr�o de design para gerenciar transa��es distribu�das,
garantindo consist�ncia de dados em sistemas onde cada microservi�o tem seu pr�prio banco de dados.
� interessante pois desacopla servi�os, melhora a escalabilidade entre outros pontos relevantes.

Descreva o seu entendimento sobre GitOps utilizando Kubernetes.
Resposta:
� a forma de gerenciar a infraestrutura e aplica�ao utilizando GIT como principal fonte das regras,
pode se definir a configura��o do cluster como pods, deployments entre outras configs em arquivos YAML
que ficam em um reposit�rio pr�prio no git.

Descreva detalhadamente algum case de sucesso em que voc� atuou diretamente no desenvolvimento para solu��o
de algum problema, cite tecnologias e os desafios enfrentados.
Resposta:
Recentemente me chegou uma demanda de integra��o com a RD Station com uma certa urg�ncia pois estava a algum tempo na responsabilidade
de outro desesenvolvedor, esta demanda se consistia na resolu��o de um problema que era referente a mensagens 'sumindo'
da fila do rabbitMQ, ap�s muitos testes diagnostiquei que o enfileirador (producer) de fato estava deixando de enfileirar
algumas mensagens por nenhum motivo aparente.
Dado esse entendimento e a urg�ncia do caso, realizei uma solu��o r�pida e eficaz que foi a remo��o do rabbitMQ
da aplica��o e realizei um 'enfileiramento' utilizando banco de dados e status para cada etapa dos envios.
Desta forma consegui mapear todas as etapas de todas os envios atrav�s de querys no banco de dados,
o servi�o no geral perdeu um pouco de velocidade de desempenho por�m o problema foi sanado.