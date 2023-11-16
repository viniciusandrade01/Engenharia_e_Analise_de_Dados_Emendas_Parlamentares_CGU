# EMENDAS PARLAMENTARES CGU - ENGENHARIA E ANALISE DE DADOS

- Para entendermos o que são as emendas parlamentares, precisamos ter em mente que o ciclo orçamentário é composto por quatro grandes fases: 
    - 1) elaboração da proposta pelo Poder Executivo;
    - 2) apreciação legislativa pelo Congresso Nacional;
    - 3) execução pelo Poder Executivo e;
    - 4) controle e avaliação pelo Congresso Nacional, com apoio do Tribunal de Contas da União (TCU).

- Nesse contexto, a emenda parlamentar é um instrumento que o Congresso Nacional pode utilizar na fase de apreciação legislativa para influir no processo de elaboração do orçamento anual. Tais emendas podem acrescentar, suprimir ou modificar determinados itens (rubricas) do projeto de lei orçamentária enviado pelo Executivo. Ou seja, por meio das emendas parlamentares os deputados e senadores podem opinar ou influir na alocação de recursos públicos em função de compromissos políticos que assumiram durante seu mandato, tanto junto aos estados e municípios quanto a instituições.

- Os tipos de emenda parlamentar são:
    - 1) individuais: propostas por cada parlamentar;
    - 2) de bancada: de autoria das bancadas estaduais no Congresso Nacional relativa a matéria de interesse de cada Estado ou do Distrito Federal;
    - 3) de comissão: apresentadas pelas comissões técnicas da Câmara e do Senado, bem como as propostas pelas Mesas Diretoras das duas Casas;
    - 4) do relator: de autoria do deputado ou senador que, naquele determinado ano, foi escolhido para produzir o parecer final (relatório geral) sobre o Orçamento. Há ainda as emendas dos relatores setoriais, destacados para dar parecer sobre assuntos específicos divididos em dez áreas temáticas do orçamento.

- Os parlamentares apresentam suas propostas de emendas ao orçamento da mesma maneira que realizam emendas a outros projetos em tramitação no Congresso. Nesse caso, as alterações são feitas ao Projeto de Lei Orçamentária Anual (PLOA). A apresentação das emendas é feita na Comissão Mista de Planos, Orçamentos Públicos e Fiscalização (CMO), que, entre outras funções, é responsável por avaliar o PLOA. Depois de aprovado na CMO e em sessão plenária conjunta do Congresso, o Orçamento é enviado novamente ao Executivo, para ser sancionado pelo presidente da República, transformando-se, portanto, na LOA.

Fonte: Agência Senado

- OBS.: ESSE PROJETO NÃO É UMA RECOMENDAÇÃO DE INVESTIMENTO, MAS UMA INICIATIVA DE FORNECER ALGUMAS INFORMAÇÕES, DADOS ÚTEIS - E PÚBLICOS - AOS INVESTIDORES/INTERESSADOS E INSIGHTS.

---------------------------------------------------------------------------------------------
# PROJETO
- Levando em conta a riqueza de dados relacionados às emendas parlamentares, farei um estudo sobre como esses recursos públicos foram, e estão, sendo empregados, abordando alguns pontos principais, como, por exemplo:
- A) Evolução anual dos valores empenhados (âmbito geral);
- B) Ordenação dos setores mais "amparados", isto é, setores que tiveram mais valores destinados;
- C) Demonstração do setor, a cada ano, que se destaca mais, que foi mais assistido;
- D) A partir das funções destaques anuais - abordada no tópico anterior, sinalize as subfunções e contagens;
- E) Análise histórica dos tipos de emendas por ano, ordenações e predominâncias;
- F) Identificação do top 3 de autores de emenda, sinalizando os mais atuantes;
- G) Agrupe por ano e calcule a somatória de valor empenhado e inscrito.

- Para conclusão desse projeto - abordando obtenção dos dados, tratamento, armazenamento deles e geração de gráficos -, foram necessárias algumas etapas, sendo elas:

---------------------------------------------------------------------------------------------
# ETAPAS

# 1) Configuração de Acessos
- Visando uma melhor organização das informações de configurações, inseri as informações necessárias, e de acessos, em um arquivo json, de nome 'data' - localizado dentro da pasta utils -, nesse arquivo há informações pertinentes a fonte extraída, o tipo do arquivo a ser gerado, parâmetros, credenciais da conta cloud AWS - usuário IAM, links necessários, informações essas pré-selecionadas pelo usuário;

# 2) Criei um processo ETL:
- E: Extração dos dados respectivos oriundos da fonte "https://portaldatransparencia.gov.br/download-de-dados/emendas-parlamentares/UNICO" e que serão inseridos no S3 Bucket, da AWS, visando garantir integridade dos dados;

- T: Fiz os tratamentos necessários para deixar os dados limpos, com sua tipificação correta e, por consequência, tê-los de maneira apropriada para obtenção/geração de gráficos/insights.

- L: Logo após os tratamentos, e tendo um dataframe preparado, carreguei os dados em um arquivo csv - nomeado com a estrutura padrão: 'Emendas_[%Y%m].csv', para ter em mãos um arquivo tratado, limpo e em conformidade, disponível para ser utilizado como ferramenta para obtenção de insights.

# 3) Desenvolvimento e Análise de Gráficos:
- Agora, inserindo um pouco sobre a função do Analista, farei algumas análises quanto aos dados coletados da CGU, levantando hipóteses e cenários.

# A) Evolução anual dos valores empenhados (âmbito geral);
- Quanto à evolução dos valores empenhados ao longo dos anos (na imagem Evolucao_Empenhados_Anual.png), é notório que há duas ascensões bem vísiveis e que chamam a atenção, sendo elas nos anos de 2016 e 2020.
    - -> Conforme as pesquisas, quanto ao ano de 2016, os valores empenhados foram, em sua maioria - representando um pouco mais de 70% do valor empenhado no ano - destinados ao setor de Assistência Social (38.63%) - atendendo, principalmente, o subsetor de Assistência Comunitária (99.48%) - e Saúde (30.94%) - atendendo alguns principais subsetores, sendo eles: Assistência Hospitalar e Ambulatorial (57.37%), Administração Geral (15.88%), Atenção Básica (11.98%), Vigilância Epidemiológica (5.99%) etc-. Dentro de diversos acontecimentos ainda nesse ano de 2016, um que ficou marcado foi o impeachment da ex-presidente Dilma Rousseff, o que caracterizou, no período, um momento de crise econômica latente - alto indicativo para que esse valor de emenda tenha sido incomum. Ainda nesse período, quanto às destinações de emendas, é visível que mais que 95% tenha sido realizada por emendas individuais - lembrando que com o impeachment, quem assumiu foi o ex-presidente Michel Temer, e, passando agora, a ter um grande apoio do 'centrão'.
    - -> CONTINUAR

# B) Ordenação dos setores mais "amparados", isto é, setores que tiveram mais valores destinados;
- 

# C) Demonstração do setor, a cada ano, que se destaca mais, que foi mais assistido;
- 

# D) A partir das funções destaques anuais - abordada no tópico anterior, sinalize as subfunções e contagens;
- 

# E) Análise histórica dos tipos de emendas por ano, ordenações e predominâncias;
- 

# F) Identificação do top 3 de autores de emenda, sinalizando os mais atuantes;
- 

# G) Agrupe por ano e calcule a somatória de valor empenhado e inscrito.
- 

# H)
- 

---------------------------------------------------------------------------------------------
# OBSERVAÇÕES:
- 

- 

- 
---------------------------------------------------------------------------------------------
# CONCLUSÃO (OPINIÃO):
- 
- 
- 
- 
- 
- 
- 
- 

------------------------------------------------------------------------------------------------
# REFERÊNCIAS:
- Sites que podem contribuir à realização das etapas acima, e que me ajudaram para obtenção do resultado final e esperado:

- https://portaldatransparencia.gov.br/emendas
- https://www12.senado.leg.br/noticias/materias/2016/12/28/impeachment-de-dilma-rousseff-marca-ano-de-2016-no-congresso-e-no-brasil
- 
- 

------------------------------------------------------------------------------------------------
# CONSIDERAÇÕES FINAIS:
Obrigado pela interação. Fico à disposição e disponível para receber dicas ou sanar dúvidas/curiosidades. Bons estudos e fica na paz!