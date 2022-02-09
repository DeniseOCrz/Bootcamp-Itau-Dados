# Bootcamp-Itau-Dados
 Bootcamp de Dados oferecido pelo Itaú em parceria com a Let's Code

Etapas do Desenvolvimento de Variáveis para o Ambiente Salesforce

1.0 - Premissas para o desenvolvimento de variáveis

	1.1 - Dados no Hadoop
	1.2 - Acessos as bases origem via Catálogo de Dados
	1.3 - Acesso ao Data Factory
	1.4 - Acesso ao GHP00145
	
2.0 - Ferramentas/Documentos/Cerimônia de Apoio

	2.1 - Ferramentas
	2.1.1 - Catálogo de Dados
	2.1.2 - Brainr
	2.1.3 - Splunk
	2.1.4 - Data Factory
	2.1.5 - Git do Máquina de Engajamento
	2.1.1 - Equipe Migração SAS | DED & CRM ??
	
	2.2 - Documentos
	2.2.1 - Planilha de Requisitos (Utilizar o modelo de Requisitos)
	2.2.2 - Planilha de Controle de Variáveis (Utilizar o modelo de Aquisição)
	2.2.3 - Planilha de Controle de Ingestão (Utilizar o modelo da Denise)
	
	2.3 - Cerimônia de Apoio
	2.3.1 - Alinhamento de Pontos Focais
	2.3.2 - GT de Variáveis
	
	## Sugestão: Incluir uma etapa para definição de Papéis e responsabilidades

3.0 - Equipes Envolvidas no Maquina de Engajamento

	3.1 - Squad EADA
	3.2 - Squad Negócios Maquina Engajamento (Ex: CRM/Aquisição)
	3.3 - Squad Negócios Move In (Ex: Token/Credito/PJ) 

3.0 - Definição da Jornada/Campanha

	Nesta etapa, os representantes da 3.2 - Squad Negócios Maquina Engajamento precisam preencher a 2.2.1 - Planilha de Requisitos para definir os contextos e as regras que serão aplicadas na jornada e realizar o 2.3.1 - Alinhamento de Pontos Focais. É nesta etapa que definimos os critérios para comunicar o cliente, e as variáveis que serão necessárias para atender estes critérios.
	
	Ex: 


4.0 - Mapeamento de variáveis e origens

	Nesta etapa, com a 3.0 - Definição da Jornada/Campanha em mãos, teremos que identificar as bases origens necessárias para viabilizar a construção destas variáveis. No mapeamento podemos identificar as origens em múltiplas plataformas de dados. Ex: Hadoop, SAS, Teradata, Oracle, DB2, SQL Server.
	Importante atualizar a 2.2.1 - Planilha de Controle de Variáveis para documentação e avaliação de esforço no 2.3.1 - GT de Variáveis

	Ex:
		○ Variável: Data do Desbloqueio do Cartão | Origem: RT2.RT2_AI6_GERCA20_GE_BASE_CDF03 | Plataforma: Hadoop
		○ Variável: Canal de Venda do Cartão | Origem: CANAL_VENDA_CARTOES_202201 | Plataforma: SAS

5.0 - Consulta/Cadastro de Elementos no Brainr

	Nesta etapa, com o 4.0 - Mapeamento de Variáveis e Origens em mãos, temos que consultar se existem elementos equivalentes a estas variáveis, cadastrados no Brainr. 
	
	Premissas: 
		○ Variável/Elemento: Data do Desbloqueio do Cartão
			▪ Consulta por termos do nome lógico da variável 
			▪ Não incluir preposições (de, da, e etc.)
			▪ Os termos precisam existir no Brainr, importante pesquisar sempre no singular. 
	
	5.1 - Consulta de Elementos
	
		# Em Construção
	
	5.2 - Cadastro de Elementos
	
		# Em Construção
	
	5.3 - Atualização do 4.0 - Mapeamento de Variáveis e Origens 

6.0 - Pré-Ingestão de Dados Manuais (Move In)

	Nesta etapa, com o 4.0 - Mapeamento de Variáveis e Origens em mãos, temos que entrar em contato a área responsável pela geração da base SAS que será cadastrada no Move In. A finalidade do contato é para definir:

		6.1 - Diretório que será disponibilizada a base SAS
		6.2 - Atributos necessários na base (nome físico, nome lógico)
		6.3 - Conceituação da base (nome físico, nome lógico, e conceituação)
		6.3 - Periodicidade e responsável da atualização da base
		6.4 - Realizar etapa de 5.0 - Consulta/Cadastro de Elementos no Brainr para os campos da base do Move In

	Definidos estes pontos, devemos prosseguir para consulta/criação de elementos no BRAINR.

7.0 - Ingestão de Dados Manuais (Move In)

	Incluir a etapa de alinhamento (via e-mail)
	
	# Em Construção

8.0 - Desenvolvimento das Tabelas Especializadas

	Neste etapa, O desenvolvedor terá como objetivo a criação ou alteração de tabelas especializadas, bem como o desenvolvimento dos códigos para o processamento destas tabelas. O material disponibilizado em 4.0 - Mapeamento de variáveis e origens proverá os insumos das bases origens, variáveis origens e finais necessárias à entrega planejada, conforme as regras definidas na própria documentação.

	8.1 - A Tabela Especializada 

		É uma base de dados que contém informações tratadas para determinada finalidade. No caso do Máquina de Engajamento, são as tabelas com dados cadastrais, transacionais, de produtos, etc. que alimentam os Data Streams do Salesforce CDP e que têm por finalidade a ativação de Jornadas e Campanhas.

		8.1.1 - Criação de uma nova Tabela Especializada 

		8.1.2 - Adicionar campos em uma Tabela Especializada existente

	8.2 - Versionamento e controle de código (Git)

		O projeto de dados para o Máquina de Engajamento é complexo e envolve áreas diversas muitas vezes desenvolvendo novas variáveis nas mesmas tabelas, portanto, controle e o versionamento destes códigos se torna necessário. Neste cenário, o desenvolvedor utilizará o repositório do Máquina de Engajamento no GitLab:
		https://git.prod.cloud.ihf/guighor/maquina-engajamento

		8.2.1 - O repositório: estrutura das pastas e arquivos

			O repositório Git é um ambiente cloud que armazena arquivos e as versões diferentes destes arquivos. Foi elaborada uma estrutura de pastas e arquivos conforme a seguir:
	 
			▪ dev/: armazena os arquivos utilizados para o desenvolvimento
				□ dev/notebook_desenvolvimento.ipynb: notebook jupyter que lê o HQL de uma tabela especializada e o "transforma" para possibilitar a execução em ambiente de desenvolvimento (Ex.: cria as tabelas temporárias e a tabela especializada em um GHP);
			▪ doc/: armazena as documentações das Tabelas Especializadas
			▪ hom/: armazena os arquivos utilizados e gerados para homologação de uma Tabela Especializada
				□ hom/notebook_homologação.ipynb: notebook jupyter que efetua análises quantitativas de uma Tabela Especializada informada
				□ hom/vX.X.X/AAAAMMDD/: estrutura de pastas que armazena arquivos HTML com os resultados gerados à partir do notebook de homologação da versão X.X.X, executado no dia AAAAMMDD
			▪ hql/: armazena os códigos .HQL responsáveis pelo processamento das Tabelas Especializadas
			▪ README.md: arquivo com o Leia-me do repositório, contém informações básicas acerca do mesmo
			▪ CONTRIBUINDO.md: arquivo tutorial de como contribuir com o repositório em um fluxo de trabalho padrão

		8.2.2 - Acessos
			O desenvolvedor deverá solicitar acesso ao Git no grupo GSI:
			
			Plataforma:	Windows 2000
			Ambiente: 	ITAU.CORP.IHF
			Aplicação:	EA9
			Grupo: 	G_CLOUD_TOOLS_GIT
			
		8.2.3 - Instalação e configuração
		
			▪ Instalar o Git mais recente pela Central de Software;
			▪ Abrir o executável Git Bash, linha de comando com funcionalidades Linux, específica do Git;
			▪ Configurar seu nome e e-mail no ambiente do Git:
				git config --global user.name “Nome Completo"  
				git config --global user.email “Marcelo.Miyazaki@itau-unibanco.com.br"
			▪ Configurar a chave SSH:
				□ Gerar sua chave SSH via Git Bash com o comando: 
					ssh-keygen -t rsa -C "email@itau-unibanco.com.br" -b 4096
				□ Copiar a chave SSH com o comando: 
					cat ~/.ssh/id_rsa.pub | clip
				□ Acessar seu perfil via Web: https://git.prod.cloud.ihf/profile
				□ Selecionar no menu ao lado esquerdo pela SSH Keys
				□ Copiar a chave no campo Key e clicar no botão Add key
		
		8.2.4 - Fluxo de trabalho Git
			
			▪ Parte 1: Clonar o repositório
				
			Primeiramente é necessário clonar o repositório:
					
				git clone git@git.prod.cloud.ihf:guighor/maquina-engajamento.git
			
			
			▪ Parte 2: Mudar para o branch de development
			
			Em seguida, altera-se para o branch de development:
			
				git checkout development
			
			▪ Parte 3: Branches
			
			Então, cria-se um branch novo, para trabalhar nas mudanças da feature:
			
				git checkout -b nome_do_branch
			
			As branches, por definição, deverão iniciar com alguma das seguintes nomenclaturas:
			
				□ development-: para desenvolvimento de features;
				□ homolog-: para homologação de features;
				□ revert-: para reversão do repositório para algum commit específico;
				□ test-: para testes;
				□ master-: para produção.
				
			▪ Parte 4: Commits
			
			Atenção: seguir boas práticas, manter os commits atômicos e conforme padrão pré-definido:
			
				[YYYYRXXSPXX] Texto do commit (verbo imperativo)
			
				  YYYY: Ano da Release
				  RXX: Release XX
				  SPXX: Sprint XX
			
			▪ Parte 5: Push
			
			Executar o push para o repositório remoto, do branch criado localmente.
			
				git push
			
			Caso o repositório não exista remotamente, deve-se utilizar o comando para criar o repositório simultaneamente ao push:

				git push --set-upstream origin nome_do_branch
			
			▪ Parte 6: Merge

			Solicitar um Merge Request do branch da feature desenvolvida ao branch development.


		8.2.5 - Boas práticas Git

			▪ Manter os commits atômicos, ou seja, faça um commit para o mínimo grupo de mudanças e/ou implementações na feature desenvolvida;
			▪ Utilize verbos no imperativo para demonstrar o trabalho efetuado, tenha em mente que a mensagem do cabeçalho deve ser clara e concisa, utilize as linhas abaixo para ;
			▪ Padrão de commit: foi adotado um padrão para identificar a qual entrega se refere o commit dado "[AAAARXXSPXX]"
			▪ Padrão de nomes de branch (development-, homolog-, revert-, test-, master-).
		
		<<< ADICIONAR NAS REFERÊNCIAS >>>
			https://sourcelevel.io/blog/7-git-best-practices-to-start-using-in-your-next-commit
			https://cbea.ms/git-commit/
			https://git-scm.com/doc
			

	8.3 - Desenvolvimento das consultas HQL
	
		8.3.1 - Hive Query Language
	
		Como a tecnologia adotada para armazenamento das Tabelas Especializadas é o Hadoop File System (HDFS), a construção é feita via HQL (Hive Query Language), linguagem análoga ao SQL para esta tecnologia.
		
		<<< ADICIONAR NAS REFERÊNCIAS >>>
			https://docs.cloudera.com/HDPDocuments/HDP3/HDP-3.0.0/using-hiveql/content/hive_hive_query_language_basics.html
			https://docs.microsoft.com/pt-br/azure/hdinsight/hadoop/hdinsight-use-hive
			http://hortonworks.com/wp-content/uploads/2016/05/Hortonworks.CheatSheet.SQLtoHive.pdf
		
		8.3.2 - Boas práticas HQL
	
			- Nas cláusulas de SELECT evitar o uso de asterisco (*), prefira explicitar o nome das colunas para otimizar o desempenho das consultas;
			- Ao agrupar, caso seja possível, utilizar o WHERE ao invés do HAVING em colunas não agregadas, isso faz com que o filtro ocorra antes do agrupamento, melhorando o desempenho da consulta;
			- Evite utilizar funções e/ou cálculos nos campos das condições dos JOINS, o desempenho será pior nesses casos, para melhorar, utilize o comando CTE para criação de uma visão temporária com o campo da condição já calculado conforme necessário.
		
		<<< ADICIONAR NAS REFERÊNCIAS >>>
			https://dwgeek.com/best-practices-to-optimize-hive-query-performance.html/
			https://confluence-itau.tecnologia.prod.ops.aws.cloud.ihf/display/COE/%5BHadoop%5D+Jornada+de+conhecimento+Hadoop+CoE
		
		8.3.3 - Notebook de desenvolvimento
		
		Na pasta /dev há o notebook de desenvolvimento. Sua funcionalidade é executar determinado código .HQL produtivo em um ambiente de desenvolvimento.

	8.4 - Homologação
		8.4.1 - Notebook de homologação

	8.5 - Deploy no Git


9.0 - Implantação da Tabela Especializada no Factory

10.0 - Cadastro da base no Move Out

11.0 - Atualizar/Cadastrar Data Stream na Salesforce

12.0 - Relacionamento entre os Data Stream

13.0 - Montagem da Segmentação

14.0 - Ativação

FAQ Maquina Engajamento

	P: Por que os dados precisam estar no Hadoop?
	R: Condição estabelecida nas Inceptions do Maquina de Engajamento, onde tal condição foi definida não só para a geração dos dados especializados, mas também para construção da solução do Data Move Out, onde o mesmo captura os dados do HDFS e realiza upload para o bucket S3 da AWS.
	
	P: Por que preciso fazer a transformação dos dados no Data Factory?
	R: O Data Factory é uma ferramenta construída pela Esfera Analytics para atender a demanda de transformação de dados do banco. Com esta ferramenta, garantimos a governança desde a origem até o dado transformado, cadastro de dependências, agendamento de workflows, rastreabilidade dos processamentos, versionamento dos códigos, e recursos parametrizáveis para utilizar no HQL.

	P: Por que preciso ingerir os dados SAS via Move In?
	R: A premissa do projeto Maquina de Engajamento, é trabalhar apenas com dados governados do Data Lake, ou seja, dados que estejam devidamente catalogados, . Seguindo este principio, temos
	
	P: Por que preciso utilizar o Move Out?
	R: Ferramenta vital para o fluxo de dados do Maquina, o Move Out é o recurso que irá transportar os dados disponibilizados no HDFS para bucket S3 da AWS que será consumido pelo HH8 que fará a transmissão para a Salesforce

	P: Por que preciso versionar as mudanças de código no GIT?
	R: Com a adesão de múltiplas equipes ao projeto do Máquina de Engajamento existe a necessidade de manter os códigos organizados de forma que não se percam atualizações e mudanças efetuadas por diferentes indivíduos trabalhando nos mesmos códigos simultaneamente.





Etapa 01 - Identificação das Variáveis da Sprint
Etapa 02 - Identificação das Bases Origens
Etapa 03 - Definição do Metadados das Tabelas Finais
Etapa 04 - Identificação/Cadastro dos Elementos no Brainr
Etapa 05 - Ingestão Produtiva (origens Sistêmicas)
Etapa 06 - Ingestão Move In (origens SAS)
Etapa 07 - Desenvolvimento do HQL
Etapa 08 - Criação das Tabelas no Data Factory
Etapa 09 - Catalogação das Tabelas no Catálogo de Dados
Etapa 10 - Solicitação de Acesso via Catalogo de Dados
Etapa 11 - Solicitação de GRANT ALL p/ usuário Data Factory
Etapa 12 - Solicitação de GRANT ALL p/ usuário Move Out
Etapa 13 - Implantação do HQL no Data Factory

Dados Bureau

Os dados de telefone e email 

Problema do Pré Processamento

Limitação do Factory para processar diversas referencias em um workflow com mais de uma tabela.
