# Hospital Fundamental (Parte 1)

Estudo de banco de dados

Analise a seguinte descrição e extraia dela os requisitos para o banco de dados: O hospital necessita de um sistema para sua área clínica que ajude a controlar consultas realizadas. Os médicos podem ser generalistas, especialistas ou residentes e têm seus dados pessoais cadastrados em planilhas digitais. Cada médico pode ter uma ou mais especialidades, que podem ser pediatria, clínica geral, gastroenterologia e dermatologia. Alguns registros antigos ainda estão em formulário de papel, mas será necessário incluir esses dados no novo sistema.

Os pacientes também precisam de cadastro, contendo dados pessoais (nome, data de nascimento, endereço, telefone e e-mail), documentos (CPF e RG) e convênio. Para cada convênio, são registrados nome, CNPJ e tempo de carência.

As consultas também têm sido registradas em planilhas, com data e hora de realização, médico responsável, paciente, valor da consulta ou nome do convênio, com o número da carteira. Também é necessário indicar na consulta qual a especialidade buscada pelo paciente.

Deseja-se ainda informatizar a receita do médico, de maneira que, no encerramento da consulta, ele possa registrar os medicamentos receitados, a quantidade e as instruções de uso. A partir disso, espera-se que o sistema imprima um relatório da receita ao paciente ou permita sua visualização via internet.

## Os Segredos do Hospital (Parte 2)

E não era exatamente aquilo!
 
Após a primeira versão do projeto de banco de dados para o sistema hospitalar, notou-se a necessidade de expansão das funcionalidades, incluindo alguns requisitos essenciais a essa versão do software. As funcionalidades em questão são para o controle na internação de pacientes. Será necessário expandir o Modelo ER desenvolvido e montar o banco de dados, criando as tabelas para o início dos testes.
Considere a seguinte descrição e o diagrama ER abaixo:

#### Entender do assunto
Considere a seguinte descrição e o diagrama ER abaixo:
No hospital, as internações têm sido registradas por meio de formulários eletrônicos que gravam os dados em arquivos. 
Para cada internação, são anotadas a data de entrada, a data prevista de alta e a data efetiva de alta, além da descrição textual dos procedimentos a serem realizados. 
As internações precisam ser vinculadas a quartos, com a numeração e o tipo. 
Cada tipo de quarto tem sua descrição e o seu valor diário (a princípio, o hospital trabalha com apartamentos, quartos duplos e enfermaria).
Também é necessário controlar quais profissionais de enfermaria estarão responsáveis por acompanhar o paciente durante sua internação. Para cada enfermeiro(a), é necessário nome, CPF e registro no conselho de enfermagem (CRE). A internação, obviamente, é vinculada a um paciente – que pode se internar mais de uma vez no hospital – e a um único médico responsável.

#### Mãos a obra?
Faça a ligação do diagrama acima ao diagrama desenvolvido na atividade antrior, construindo relacionamentos com entidades relacionadas. E eleve o seu diagrama para que já selecionando os tipos de dados que serão trabalhados e em quais situações. 

Por último, crie um script SQL para a geração do banco de dados e para instruções de montagem de cada uma das entidades/tabelas presentes no diagrama completo (considerando as entidades do diagrama da atividade anterior e as novas entidades propostas no diagrama acima). Também crie tabelas para relacionamentos quando necessário. Aplique colunas e chaves primárias e estrangeiras.
Use ferramentas, como ERPlus, Lucidchart, draw.io (via web) e MySQL Workbench, ou mesmo um editor de imagens para o diagrama. 

Você pode utilizar o MySQL Workbench ou o DBdiagram.io para montar os scripts SQL.

## O Prisioneiro dos Dados (Parte 3 - Alimentando o banco de dados)

De que serve o banco sem dados? 
Então vamos alimentar o banco! 

Com o banco de dados para o sistema hospitalar completamente montado, é necessário incluir dados para realizar os devidos testes e validar sua viabilidade quanto ao sistema. Nesta etapa, também é importante realizar a separação de alguns scripts iniciais para o banco, com os dados que serão necessários a um povoamento inicial do sistema.

Jogando nas regras que você criou: 
Crie scripts de povoamento das tabelas desenvolvidas na atividade anterior
Observe as seguintes atividades: 

- Inclua ao menos dez médicos de diferentes especialidades.

- Ao menos sete especialidades (considere a afirmação de que “entre as especialidades há pediatria, clínica geral, gastrenterologia e dermatologia”).

- Inclua ao menos 15 pacientes.

- Registre 20 consultas de diferentes pacientes e diferentes médicos (alguns pacientes realizam mais que uma consulta). As consultas devem ter ocorrido entre 01/01/2015 e 01/01/2022. Ao menos dez consultas devem ter receituário com dois ou mais medicamentos.

- Inclua ao menos quatro convênios médicos, associe ao menos cinco pacientes e cinco consultas.

- Criar entidade de relacionamento entre médico e especialidade. 

- Criar Entidade de Relacionamento entre internação e enfermeiro. 

- Arrumar a chave estrangeira do relacionamento entre convênio e médico.

- Criar entidade entre internação e enfermeiro.

- Colocar chaves estrangeira dentro da internação (Chaves Médico e Paciente).

- Registre ao menos sete internações. Pelo menos dois pacientes devem ter se internado mais de uma vez. Ao menos três quartos devem ser cadastrados. As internações devem ter ocorrido entre 01/01/2015 e 01/01/2022.

- Considerando que “a princípio o hospital trabalha com apartamentos, quartos duplos e enfermaria”, inclua ao menos esses três tipos com valores diferentes.

- Inclua dados de dez profissionais de enfermaria. Associe cada internação a ao menos dois enfermeiros.

- Os dados de tipo de quarto, convênio e especialidade são essenciais para a operação do sistema e, portanto, devem ser povoados assim que o sistema for instalado.

## A Ordem do Alterar (Parte 4- Alterando o Banco de Dados)

Hummm... 

Não... Não acabou... 
Um banco de dados pode sofrer alterações ao longo da sua concepção e do seu desenvolvimento. Nesse momento devemos nos preparar para atualizar nossas estratégias.

Mãos a Obra. 
Pensando no banco que já foi criado para o Projeto do Hospital, realize algumas alterações nas tabelas e nos dados usando comandos de atualização e exclusão:

Crie um script que adicione uma coluna “em_atividade” para os médicos, indicando se ele ainda está atuando no hospital ou não. 

Crie um script para atualizar ao menos dois médicos como inativos e os demais em atividade.

## As Relíquias dos Dados (Parte 5 - Consultas)

Uma vez que o banco estiver bem estruturado e desenhado, é possível realizar testes, simulando relatórios ou telas que o sistema possa necessitar. A tarefa consiste em criar consultas que levem aos resultados esperados.

Crie um script e nele inclua consultas que retornem:

- Todos os dados e o valor médio das consultas do ano de 2020 e das que foram feitas sob convênio.
- Todos os dados das internações que tiveram data de alta maior que a data prevista para a alta.
- Receituário completo da primeira consulta registrada com receituário associado.
- Todos os dados da consulta de maior valor e também da de menor valor (ambas as consultas não foram realizadas sob convênio).
- Todos os dados das internações em seus respectivos quartos, calculando o total da internação a partir do valor de diária do quarto e o número de dias entre a entrada e a alta.
- Data, procedimento e número de quarto de internações em quartos do tipo “apartamento”.
- Nome do paciente, data da consulta e especialidade de todas as consultas em que os pacientes eram menores de 18 anos na data da consulta e cuja especialidade não seja “pediatria”, ordenando por data de realização da consulta.
- Nome do paciente, nome do médico, data da internação e procedimentos das internações realizadas por médicos da especialidade “gastroenterologia”, que tenham acontecido em “enfermaria”.
- Os nomes dos médicos, seus CRMs e a quantidade de consultas que cada um realizou.
- Todos os médicos que tenham "Gabriel" no nome. 
- Os nomes, CREs e número de internações de enfermeiros que participaram de mais de uma internação.
Observação 1: se necessário, inclua novos registros no banco de dados para testar adequadamente.  

Observação 2: podem ser úteis as funções de data do MySQL, como DATEDIFF(data1, data2) para número de dias entre duas datas, CURDATE() ou NOW() para data atual, DATE(dataehora) para extrair a data de um “datetime”, YEAR(data) para o ano de uma data, TIMESTAMPDIFF(YEAR, data1, data2) para número de anos entre duas datas, entre outras. 
Consulte a documentação do MySQL (“Date and Time Functions”) para mais informações.
