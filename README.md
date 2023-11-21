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
- B) Demonstração do setor, a cada ano, que se destaca mais, que foi mais assistido;
- C) A partir das funções destaques anuais - abordada no tópico anterior, sinalize as subfunções e contagens;
- D) Análise histórica dos tipos de emendas por ano, ordenações e predominâncias e identificação do top 3 de autores de emenda, sinalizando os mais atuantes;
- F) Agrupe por ano e calcule a somatória de valor empenhado e inscrito.

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
- Quanto à evolução dos valores empenhados ao longo dos anos (conforme imagem Evolucao_Empenhados_Anual.png), é notório que há duas ascensões bem vísiveis e que chamam a atenção, sendo elas nos anos de 2016 e 2020.
    - -> Conforme as pesquisas, quanto ao ano de 2016, os valores empenhados (conforme imagem Evolucao_Empenhados_Anual.png) foram, em sua maioria - representando um pouco mais de 70% do valor empenhado no ano - destinados ao setor de Assistência Social (38.63%) - atendendo, principalmente, o subsetor de Assistência Comunitária (99.48%) - e Saúde (30.94%) - atendendo alguns principais subsetores, sendo eles: Assistência Hospitalar e Ambulatorial (57.37%), Administração Geral (15.88%), Atenção Básica (11.98%), Vigilância Epidemiológica (5.99%) etc-. Dentro de diversos acontecimentos ainda nesse ano de 2016, um que ficou marcado foi o impeachment da ex-presidente Dilma Rousseff, o que caracterizou, no período, um momento de crise econômica latente - alto indicativo para que esse valor de emenda tenha sido incomum. Ainda nesse período, quanto às destinações de emendas, é visível que mais que 95% tenha sido realizada por emendas individuais (conforme - lembrando que com o impeachment, quem assumiu foi o ex-presidente Michel Temer, e, passando agora, a ter um grande apoio do 'centrão'.
    - -> Quanto ao ano de 2020, não podemos esquecer que o mundo, ainda, passava por um evento que mexeu, e ainda movimentada, nas estruturas mundiais: a pandemia (COVID-19). Por conta disso, o governo, importantíssimo nesse cuidado, precisava destinar recursos para subsidiar os principais setores, mas agora dando um foco a saúde - local que foi maior movimentado e requisitado. Dessa forma, conforme visualizamos nos gráficos (conforme imagem Evolucao_Empenhados_Anual.png e Setor_Destaque_Anual.png), percebemos que nesse ano, foi o maior valor empenhado/reservado às emendas, ultrapassando a casa de 35 bilhões de reais. E quanto ao autor que maior movimentou recursos nesse período (conforme imagem Top3_Autor_Emendas_2020.png), podemos destacar o Relator Geral e Átila Lins;
    Obs.: Existe à presença de autores 'sem informação' no nome, por isso, foram classificados como 'Sem Informação'.

# B) Demonstração do setor, a cada ano, que se destaca mais, que foi mais assistido;
- Nesse tópico, posso observar (conforme imagem Setor_Destaque_Anual.png) o top 1 dos setores mais amparados/assistidos a cada ano. É possível ver, que desde 2014 - início dos dados que tenho em mãos e é disponibilizado, pude perceber que o setor mais destacado é o da Saúde (conforme imagem Setores_Destacados_Anual_[%Y].png - sendo %Y representação de ano, contendo 4 dígitos -).

# C) A partir das funções destaques anuais - abordada no tópico anterior, sinalize as subfunções e contagens;
- Tendo o setor referência a cada ano, sinalizei os subsetores e suas respectivas contagens, isto é, quantas vezes o setor foi amparado (conforme Subfução_dos_Setores_Destacados_Anual_[%Y].png - sendo %Y representação de ano, contendo 4 dígitos -). Como já sabemos que o setor destaque é o da Saúde, percebemos que o top 3 dos subsetores são: Assistência Hospitalar e Ambulatorial ( ambulatorial e hospitalar, capacitado para prestar atendimento ospitalar, capacitado para prestar atendimento aos casos de reabilitação que justifiquem uma intervenção mais freqüente e
intensa, requerendo tecnologia de alta complexidade e recursos humanos mais especializados. Importante que tenha caráter docente e assistencial, vinculado aos centros universitários ou formadores de recursos humanos e, ainda, promovam, em conjunto com os demais níveis, formulação de instrumentos de avaliação da eficiência e eficácia do processo de reabilitação e impactos alcançados na região), Atenção Básica (intervenções de caráter individual, familiar, grupal e comunitária, com vistas a favorecer a inclusão social, exemplos: orientações para a mobilidade
de portador de deficiência visual, prevenção de deformidade mediante posturas adequadas, estimulação da fala para portadores de distúrbios de comunicação. As ações serão desenvolvidas por familiares ou agentes comunitários capacitados e supervisionados, com avaliação constante e sistematizada) e Administração Geral, ou seja, esses 3 subsetores são os mais amparados anualmente, justamente por serem a 'espinha dorsal' do setor da saúde.

# D) Análise histórica dos tipos de emendas por ano, ordenações e predominâncias e identificação do top 3 de autores de emenda, sinalizando os mais atuantes;
- Já quanto aos tipos de emendas (conforme imagem Tipos_Emendas_em_[%Y].png), podemos perceber a predominância das Emendas Individuais (que é a lógica e mais esperado), seguida pelas Emendas de Bancadas (emendas coletivas, de autoria das bancadas estaduais/regionais) e Emendas do Relator (deputador/senador escolhido para reproduzir o Relatório Final do Orçamento).

# F) Agrupe por ano e calcule a somatória de valor empenhado e inscrito.
- Quanto a analise dos valores empenhados e inscritos (dívidas para o próximo ano), percebemos que desde 2014 - ano inicial que tivemos acesso - os valores empenhados sempre foram acima dos valores de dívidas para o próximo ano, ou seja, a dívida do ano era 'paga' por conta da reserva. Entretanto, em 2021, ainda em um ambiente de pandemia, tivemos um valor de dívida acima do valor empenhado, razão 'justa', justamente por conta desse fato mundial - e pelo cenário naquele momento, pegando uma rebarba do ano ápice, que foi o ano anterior, ano de 2020 -. Desconsiderando esses anos de pandemia (de 2019 a 2022), podemos perceber que os valores de dívidas são considerados bem baixos, em relação ao valor empenhado, ou seja, os anos na qual foram incomuns, são os anos da pandemia.

---------------------------------------------------------------------------------------------------
# OBSERVAÇÕES:
- Os gráficos separados por ano, facilitam na compreensão macro de como essa estrutura de emendas é organizada e tocada. Interessantíssima essas separações, movimentações e organizações, justamente por se tratar de recursos públicos sendo destinados. Dando uma visão geral aos usuários finais, usuários que usufruem dessas destinações. É importante ver se está chegando na outra ponta.

---------------------------------------------------------------------------------------------------
# CONCLUSÃO (OPINIÃO):
- Posso concluir que, conforme às pesquisas, percebo que os valores empenhados vêm tendo um aumentado ao decorrer dos anos - correções, que o setor mais amparado é o da saúde - justamente por ser um setor crítico e super importantíssimo para o desenvolvimento e manutenção do país -, com uma proporcionalidade de 3 pra 1, isto é, 3 investimentos na área da saúde e 1 para o setor segundo lugar (que, geralmente, é o Setor de Urbanismo).

- Quanto aos autores de emendas, o esperado acontece, o autor mais destacado são os 'Individuais' - Emendas Individuais. Agora, pra mim, o segundo me chamou atenção, sendo o Relator. Eu pensava que o segundo era ocupado pela bancada - Emendas da Bancada, justamente por estarem em favor de causas 'específicas' -, mas podemos levantar a importância do Relator, justamente por estar encabeçando, prestando um auxílio mais 'pontual'.

- Foi um projeto bastante interessante, conseguir compreender mais um pouco sobre como funciona às emendas, os setores mais amparados, os tipos de autores mais envolvidos e os autores que se destacam mais.

------------------------------------------------------------------------------------------------
# REFERÊNCIAS:
- Sites que podem contribuir à realização das etapas acima, e que me ajudaram para obtenção do resultado final e esperado:

- https://portaldatransparencia.gov.br/emendas
- https://www12.senado.leg.br/noticias/materias/2016/12/28/impeachment-de-dilma-rousseff-marca-ano-de-2016-no-congresso-e-no-brasil
- https://bvsms.saude.gov.br/bvs/publicacoes/colec_progestores_livro9.pdf

------------------------------------------------------------------------------------------------
# CONSIDERAÇÕES FINAIS:
Obrigado pela interação. Fico à disposição e disponível para receber dicas ou sanar dúvidas/curiosidades. Bons estudos e fica na paz!