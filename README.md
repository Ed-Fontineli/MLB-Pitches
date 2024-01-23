# Projeto de Ciência de Dados com os arremessos da MLB de 2015-2019
rojeto de ciÊncia de dados utilizando a  base de dados do [ Kaggle](https://www.kaggle.com/code/lucasdataartist/mlb-pitch-data-2015-8-visualization-only-plt-sns), mas utilizando somente o arquivo pitches_2019, o projeto foi escrito na linguagem Python. Os dados estão no formato CSV e contém informações sobre  cada arremesso dessas temporadas com os dados atribuídos a cada jogada. A ideia principal do projeto é tentar encontrar as melhores variáveis que expliquem o que leva ao **strike**, que é um dos principais objetivos do arremessador, onde o strike acontece (`strike = 1`) ou não (`strike = 0`), ou seja, queremos entender quais as principais bases estatísticas que podem ser estudadas para auxiliar o arremessador a atingir o máximo de strikes posssíveis com base nas diversas variávies que possuímos nessa base de dados. OBS: serão levados em conta apenas as estatisticas dos arremessos, deixando de lado a parte dos rebatedores e outros fatores.
Uma descrição completa dos atributos está abaixo.

|Campo|Descrição|
|:-|:-|
|px| Posiçao da bola no eixo x em relação ao homeplate |
|pz| Posiçao da bola no eixo y em relação ao homeplate |
|start_speed| Velocidade inicial|
|end_speed| Velocidade final|
|spin_rate| Rotações por minuto da bola|
|spin_dir| Direçao da Rotação da bola|
|break_angle| Ângulo da quebra da bola|
|break-lenght| Comprimento da quebra|
|break_y| Quebra no eixo y|
|ax| Aceleração do arremesso no eixo x|
|ay| Aceleração do arremesso no eixo y|
|az| Aceleração do arremesso no eixo z|
|sz_top| Distância entre o chão e o topo da zona de strike do rebatedor |
|sz_bot| Distância entre o chão e o final da zona de strike do rebatedor |
|type_confidenca| O peso no nó de saída do algoritmo de classificação correspondente ao tipo de pitch mais provável |
|vx0| Velocidade inicial do arremesso no eixo x |
|vy0| Velocidade inicial do arremesso no eixo y |
|vz0| Velocidade inicial do arremesso no eixo z |
|x| A localização horizontal do arremesso ao cruzar a home plate |
|x0| A localizacão horizontal inicial do arremesso |
|y| A localização vertical do arremesso ao cruzar a home plate |
|y0| a distância em pés da base onde o sistema PITCHf/x está configurado para medir os parâmetros iniciais. |
|z0| A altura inicial do arremesso|
|pfx_x|O movimento horizontal do arremesso entre o ponto inicial e a homeplate |
|pfx_z|O movimento vertical do arremesso entre o ponto inicial e a homeplate |
|nasty|Sem informação exata |
|zone| Se foi ou não dentro da zona de strike
|code| Ação da jogada |
|type| Ação da jogada|
|pitch_type| Tipo de Arremesso |
|event_num| Número de eventos |
|b_score| Número de caminhadas
|ab_id| Id do Rebatedor |
|b_count| Contagem de bolas|
|s_count| Contagem de strikes|
|outs| Contagem de foras|
|pitch_num| Número de arremessos|
|on_1b| Se chegou na primeira base|
|on_2b|Se chegou na segunda base|
|on_3b|Se chegou na terceira base|

# Utilização
A ideia de utilização se da ao fato em como as estatisticas podem ser utilizadas para ajudar o arremessador a encontrar a melhor forma de conseguir strikes e consequentemente conseguir strikeouts.

### Dependencias

Bibliotecas necessárias:

seaborn==0.12.2

matplotlib== 3.7.1

pandas==1.3.5

numpy==1.25.5

statsmodels==0.13.5

# Storytelling

Foram uilizados inicialmente todas as variáveis, e através de testes utilizando o statsmodel e o R2 como base foram sendo definidas quais variáveis seriam melhores para atingir um melhor R2. Para isso além do statsmodel também foram utilizados gráficos para análise exploratória dos dados. Então ao fim do modelo, chegou-se as seguintes conclusões:

- Num primeiro momento utilizando apenas os dados de 2019 o R2 foi bem baixo, então conclui-se que essas variáveis não são o suficiente para fazer um melhor modelo preditivo;
- Dito isto, somente foi utilizado uma parte do data-set original, então provavelemnte as outras partes do "quebra-cabeças" estão nessa outra parte que contém os rebatedores e demais informações estat´sticas de outras jogadas;
- Apesar disso, as variáveis escolhidas apresenaram um a certa influência dentro do modelo, precisando apenas de mais ajuda de outras variáveis;
- Num novo notebook foi-se utilizado os dados de todas as temporadas, onde mais uma vez foram utilizadas as mesmas ferramentas de analises exploratorias;
- Os gráficos mostram que os arremessos que mais conseguem strike sao a bola rapida (FF) em seguida da slider (SL), que são arremessos comuns de diversos arremessadores, o que indica o porquê gerarem mais strikeouts;
- Também são os que cedem mais walks pelo mesmo motivo;
- Com os dados de arremessos completos chegou-se a um R2 de 76%, muito maior do que o anterior, indicando que um escopo maior deu mais qualidade e poder ao modelo preditivo;
- Apesar disso, mesmo alterando as variáveis de acordo com o p-value o R2 não mudou;
- O que indica que o modelo somente pode melhorar adicionando mais variáveis no caso dos rebatedores, ou alterando o x das variáveis.

## Autores

[@EduardoFonteneli](https://www.linkedin.com/in/carlos-eduardo-fontineli-goncalves/)
