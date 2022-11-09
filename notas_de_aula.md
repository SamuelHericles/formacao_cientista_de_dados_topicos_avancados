# Inteligência Artificial Explicável

- Modelos pode ser explicado em diferentes níveis;
- Relação I:
  - Complexidade (diretamente proporcional)
  - Capacidade (diretamente proporcional)
  - explicabilidade (inversamente proporcional

- Relação II:
  - Explicabilidade (diretamente proporcional)
  - Confiança (diretamente proporcional)

- Se você precisa de XAI
  - Usar modelos com maior explicabilidade;
  - Usar técnicas que melhoram a explicabilidade dos modelos;
  - Diferntes niveis de explicabilidade.

## Porque um modelo precisa ser explicado?

- Hoje em dia, a IA está tomando muitas decisões por nós;
- Estas decisões são feitas automaticamente;
- Até que ponto podemos confiar neste modelos?
- Legislação obriga que a IA seja explicavel;
- Reputação: AI toma uma decisão preconceituosa;
- Um veículo autônomo provoca um acidente - como planejar?
- Depuração: enviesamenteo no trieno, como descobrir? Qual peso está errado? o que pode está errado?
  - Precisao, acurácia, só isso é suficiente?
  - pontos discriminatórios.
- Um modelo pode ser hackeado? Dados pode hackear o modelo!!!!!
  - One pixel attack, artigo(enviar uma imagem por isso)
- Questão pessoal, alguem quer entender o modelo(o cliente quer entender como funciona o modelo)
  - O cliente queria entender como funciona o modelo

# Conceitos de XAI

- Linear/Monotonico(retinha): correlação 1.0 (so sobe ou so desce);
- Monotonico(nao uma retinha mas cresce como uma): correlação difernte de 1.0 mas próxima (So sobe ou so desce);
- Não monotonico(não é uma retinha e não cresce como uma): correlação muito baixa;
  - durante uma reta como esta, há situação que sobe e outras que desce;
- Interpretar um modelo é uma visão de caso específico, pegar casos e casos e ver o que saí do modelo;
  - Interpretar Local e Global;
  - Global é como um todo;
  - Local são casos específicos;
- Interpretação Agnóstica vs específica
  - Agnóstica: Lime;
  - específico: Tree Shap;

# Modelos White box

- Regressão Linear;
- Regressão Logistica;
- Árvores de decisão;
- Modelos baseados em regras;
- Naive Bayes;
  - Ele julga as variaveis no ponto de vista das variáveis e considerando elas com mesma chances de ocorrer;
- Redes Bayesianas
  - O Naive bayes considera que as variaveis dependentes não tem correlação ou não, se chuveu não é porque tinha sol. Ou melhor, se há uma probabilidade condicional. Tempo com vento, ele julga que não ambas não influencia;
  - As Rede Bayesianas vai buscar a probabilidade condicional entre as variáveis e assim obter a probabilidade da variável independente;

# Modelos Black box

- Redes neurais
  - É dificil encontrar a origem das variaveis(hiperparâmetros), busca mesmo é resolver o problema. Ruim de explicar.

# Técnicas de Inteligência Artificial Explicável

- Ténicas Global: olha os dados/saídas como um todo;
- Técnicas Locais: explicar casos específico do modelo;
- Ténicas Agnóstica: tanto faz, se é específico ou não;

- Técnicas Globais:
  - Criar um workflow do modelo assim explica a arquitetura do modelo;
  - Limites de descisão
    - Visualmante ver as áreas que o modelo classifica/determina as variaveis independentes;
  - Feature importance:
    - Ver quais as características mais importantes;
    - Ver o erro de cada características;
    - mostrar qual características é mais importantes;
    - Baseado nas características, qual delas é a mais importante, ou essa, se uma características mudou de valor como ficou o erro da saida do modelo?
    - Geralmente o gráfico é: Loss: MAE x Nome da característica;
  - Individual condicional Expectation(ICE):
    - Basicamente é a visão da mudança da variável em relação ao que foi predito, além de mostrar que mostrar  frenquencia no eixo x;
    - (Frequencia x Clindros) x Predito(y):
      - Maior o cilindro maior a potencia;
  - Partial dependentes Plots(PDP):
    - Mostra a previsão média com base nas observações. Ex.: (Frequencia x Cilindro) x Predito(y);
  - Accumulated Local Effects(ALE):
    - Como que, em média, a característica influencia a potencia do motor(variável independente);
    - Mais rápido de ser gerado;
    - Técnia de agnótica, não precisa saber o tipo de modelo;
  - Feature Interation:
    - Média a interação entre características;
    - A relação de uma característica com a classe depende de outra característica;
    - Baseado na estatísitca-H;
    - Sempre entre 0 e 1 [0,1];
    - Pode ver a interação tano nos atributos entre si quanto na variável independente;
  - Surogate Model:
    - Um modelo mais simples para explicar um modelo mais complexo;
    - Modelo substituito;
    - São usado para explicar o modelo, é simples;
    - Você pode criar o próprio modelo;
    - Usar boxplot para explicar como é a saída do modelo para determinadas entradas;

- Técnicas locais:
  - Local Interpretable Model-Agnostic Explanations (Lime):
    - Com um único registro, ele mostra quais as características foram mais importante na tomada de decisão da imagem;
    - A Influencia do atributo sobre a variável dependente;
  
  - Shapley Values:
    - É técnica que se baseia na teoria dos jogos;
    - Analisa a contribuição de cada variavel a variavel dependente da amostra com a da base toda;
    - variável x phi;
    - Neutro;
- Software de mostrar o modelo de machine learning, não é python;

# Engenharia de atributos

- Melhorar as característica para melhorar o modelo;
- Técnicas para melhorar o modelo;
- Dá pra dividas a Engenharia de atributos em 5 partes:
    1. Pré-processamento;
        1. Tratamento de valores faltantes(é sim engenharia de atributos);
        2. Tratamento de outliers;
    2. Codificação de categorias;
    3. Dimensionamento de características;
    4. Geração de Extração de características;
        1. Binning;
        2. PCA;
        3. Decomposição de datas;
    5. Seleção de característica importantes;

  - Valores faltantes:
    - Há um motivo?
    - Tem modelos que não aceita;
    - Valores Números pode usar a mediana;
    - Valores categóricos pode usar a moda ou outros;

  - Outliers:
    - Não existe regra geral;
    - Pode remover ou não, tem que ver caso a caso;
      - Exemplo: idade, teto salarial etc.
    - Desvios padrão da média
    - O que fazer?
      - Remover?
      - Normalizar?

# Categorial enconding (label e One-Hot enconding)

- Algoritmos entenm Números;
- Categorial enconding é o processo de transformar categorias em Números;
- Duas formas:
  - Label enconding;
  - One-Hot enconding;

- Label enconding:
  - Cada categoria se transforma em número;
  - Problema, o modelo pode atribuir ordem aos dados, ou seja, um padrão errôneo;
  - Também, quando há um grnade número de categorias.

- One-hot enconding:
  - Cada categoria é um nova feature(coluna) é dummy values;
  - Porém, cuidado:
    - Dimmy Variable Trap: o valor dos atributos se torna altamenet previsivel
    - Resultado, correlação entre as variáveis independentes: multicolinearidade
    - Solução: Excluir um dos atributos

# Dimensionamento de característica

- Ex.: em rede neurais artificiais é melhor usar normalização para o otimizador(Grandient Descent) convergir melhor.
- Processo de transforma de dados numéricos;
- Variáveis em escalas diferentes;
- Grandient Descent converge mais rápido para o mínimo local;
- Não vai melhorar significavamente o modelo
- Arvores de decisão não precisam de nenhum tipo
- Não se aplica a atributos categóricos transformados;

- Padronizacão pode z-score:
  - média zero e desvio padrão 1;
  - Podem ser negativos;
  - Não afeta outliers;
  - Deve usado na maioria dos casos;

- Normalização Min-Max
  - $Xn = X - \frac{Xmin}{Xmax - Xmin}$
  - Na escala de [0,1], só valores positivos, por isso que é muito usado em processamento de imagens
  - Usado em processamento de imagem e RNA
  - Quando não sabemos a distribuição dos dados, por isso que é muito usado no processamento de imagens
  - É util em imagens porque os dados normalizados desta forma são sempre positivos, na z-score poderia aparecer negativo;
  - Remover outliers pois impões "Limites";
  - A normalização min max ela tentará manter a distribuição antiga dos dados, o que muda é o intervalo deles para [0,1], já na z-escore ela mudará a distruição para normal-z;
    
# Geração e Extração de característica

- Binning:
  - Quanto você tem muitas classes, então é interessante pegar as menos populosa e uni-las para dizer como "outros";
  
- PCA:
  - Alta dimensionalidade reduz a capacidade de generalização;
  - PCA é um método de redução de dimensionalidade;
  - O método cria atributos sintéticos, sem compreensão funcional;
  - Estes novos atributos buscam manter as características importantes dos dados;
  - Representação dos atributos originais: projeção;
  - Não permite avaliar importância de atributos e não mais representam o negocio analisado;

# Métricas de avaliação do modelo

- Para modelos de classificação:
  - Matrix de confusão:
    - Positivos verdadeira, recal, quanto de bons foram realmente bons corretamente;
    - Precisão, dos que dei como bons, quantos realmente era bons;
    - Especícdade, dos maus, quantos que realmente eram maus;
    - Positivos, erro to tipo, que eram bom, mas foram dados como maus;
  - F1-score:
    - Média harmonica do precision e recall;
  - Logarithm Loss:
    - Mostra a probabilidade para cada classe;
    - Bom para classificação multi-classe;
    - Penaliza a classificação errada;
    - Limite inferior zero;
    - Objetivo é minimizar;
  - Curva ROC:
    - Mostra o trade-off entre precision e recall;
  - AUC área sobre a Curva:
    - Quanto mais de aprox de um, melhor;

- Para modelos de previsão
  - Mean erro(ME):
    - Média da diff entre previso e real;
  - Mean absolute erro(MAE):
    - Mais proximo de zero melhor;
  - Roat mean squared Error(RMSE):
    - Métrica independente de escala;
    - Mais proximo de zero melhor;
  - Mean Percentage Error(MPE):
    - Difernça percentual de erro;
  - Mean absolute Percentage Error(MAPE):
    - Diff absoluta percentual de erro, sem escala;
  - Uma coisa interesante para avaiar o modelo:
    - Olhar a matriz de confusão como o negocio. Emprésitmo pro Exemplo;
    - Colocar o valor cobrado como divida do cliente na tabela de confusao;

# Métricas de agrupamento

- Vamos começar com perguntas:
    1. De fato existem Clusters nos dados?
        - sabemos que K-means irá agrupar sempre dados
        - nao porque tem dados que é possível ter grupos?
    2. O número ideal de clusters é de fato 3?
        - Usamos 3 porque conhecemos os labels?
        - esse é numero ideal?
    3. Foram produzidos bons clusters?
    4. Usamos o melhor agrupador?
        - K-means sempre vai agrupar os dados não importa se tem ou não.
- (Shopkins)Holt estatísitca para minimizar o valor e ver que os grupos estão bons.
  - quanto mais proximo de zero, menos agrupavel os dados são
  - gráficos de VET, grafico para ver os dados
  - Quanto maior o numero, o grafico vai mostrar mais dados.
  - A dica é usar o gráfico em preto e branco
  - Tecnica visual + estatitica H
- Qual o numero ideal de clusters?
  - técnia elbow ou cotovelo;
    - Número de clusters k x;
  - Average silhoutte
    - ja mostra o numero ideal;
  - Gap;
  - Hubert index;
  - D Index;
  - *** elas vão mostrar valores de k de clusters diferntes.**
- Foram produzidos bons clusters?
  - Em um bom cluser:
    - Diâmetro do cluster pequeno;
    - Distância entre os clusters deve ser grande;
  - Índice "Dunn" mede a qualidade do cluster;
  - Busca-se maximizar este índice, qunato maior melhor;
- Usamos o melhor agrupador?
  - Python técnica de comparar os melhores agrupadores;
  - Mostrar o optimal Scores;

# Função de Custo

- Basicamente se a função normal é: $y = mx+b$;
- Temos o erro que é o predito menos o real: $y_1 - \^y_1$;

    que quanto mais próximo de zero, seguindo para ambos os lados(positivo ou negativo) melhor e para facilitar usamos a equação: $\frac{1}{n} * sum(yi - \^yi)ˆ2 = e$

    a letra e de erro, mostra que quanto menor que zero melhor.

    Com isso, voltadno a equação da reta: $y = mx + b$

    as nossas partes 'móveis'  são a inclinação da reta e a constante b. Portanto o objetivo da função
    de custo é minimizar a letra e encontrar valores melhores para m e b.

# Gradiente Descente

- seja o erro associado a função $e = \frac{1}{n} * sum(yi - y^i)ˆ2$;
- o gradiente descente é basicamente uma função de gradiente para mostrar o apontamento: $/naplaE = (/rhoE//rhom, /rhoE//rohb)$;
- O logo o menor valor é o negativo:  - /naplaE = - (/rhoE//rhom, /rhoE//rohb);
- Basicamente é o gradiente negativo, derivada parcial de cada componente m e b da equação;
- Entra uma nova variável, a letra L que é o valor de custo para melhorar os valores m e b;
- O gradiente descente oferece a direção como menor taxa de mudança e atualiza o valores de m e b, é um cálculo interativo;

# Extreme Learning machine

- Chineses proposta em 2006;
- Extreme é porque é extramente rápido;
- Os pesos definidos aleatoriamente, pode ser qualquer disitruição
- Apenas uma camada oculta;
- os pesos das sinapse entre a camada oculta e a camada de saída é definido através do método dos
mínimo quadrados(inversa de moore-penrose) ao invés de Gradient Descent, não é um processo interativo;
- é o oposto de uma rede neural profunda;
- Não há processo interativo de ajustes de pesos;
- Normalmente possui uma única camada oculta;
- Controvérsias:
  - ideia antigas com novo Nome;
  - rápida, mas não generalização boa que nem MLP;
  - não é solução milagrosa;
  - ELM em algumas situações é boa;
  - Treina mais rápido e pode dar bons resultado, pode ser colocado na sua bagagem;
- Ver o atigo original dos autores;

# Conjunto de dados desbalanceados

- A maioria das transaçoes nao sao fraudulentas;
- A maioria dos pacientes nao estao doentes;
- A maioria dos clinetes nao vai abandonar a empresa;
- A mariora dos acessos a rede nao sao ataques;
- O que fazer?
  - Coletar os dados de forma balanceada;
  - Havendo dados em abudancia, gerar amostras estratificadas e balancedas;
  - Usar metricas de avaliação apropiadas;
  - Utilizar modelos que penalizam o classificador ao errar a classe miniotária;
  - gerar dados artficialmente, balanceado a classe:
    - undersampling;
    - oversampling(smote);

# Auto ML

- Tem modelos com alto custo computacional e ainda com alto risco;
- Ele serve para:
  - Automatizar o processo;
  - Reduzir a interferência humana;
  - Melhora performance computacional;
  - Melhorar a performance dos modelos;
- Ter modelos de ml mais eficientes;
- Produtos orientados a dados;
- Participar de competições de ML;
- Processo de ML:
  - Problema;
  - Fonde de Dados;
  - Pré-processamento;
  - Treinamento do modelo;
  - Teste do modelo;
  - Implantação;
- Pré-processamneto você encontra um otimo local;
- Treinamento do modelo não é facil/possivel chegar a um ótimo Global. Auto ML ajuda a chegar mais próximo;
- Não existe o 100% do modelo, é utópico;
- Hiper: são definidos antes do Treinamento;
- paramentros: sao definidos durante o treino;
- Não basta automatizar, é preciso buscar a melhor configuração de hiperparâmetros;

## Como funciona Auto ML

- Espaço de busca:
  - Quantas formas de hiperparâmetros testar;
- Estratégia de busca:
  - GridSearch;
  - RandomSearch;
  - Otimizador Bayesiano:
    - Entre os melhores modelos de otimização;
    - interativo;
    - Utilizam modelo subistituto, que tem um custo menor de otimização;
    - Avaliam resultados dos modelos  resultantes antes de escolher os novos hiper parâmetros para os próximos modelos;
  - Algortimos Genéticos: melhores configurações levam para próxima geração;
  - CMA-ES: convariance matrix evolutionary strategy;
  - Optuna;
- Medidade de performance:
  - MPE, MAE, MAPE;

# Multi Fidelity

- Cross validation;
- testar com features difernte;
- numero de configurações diferentes;
- curva de aprendizado;

# Classificação MultiLabel

- Muito importante e pouco falado;
- binário: 0 ou 1;
- multilabel: 0, 1, 2 ....(pode ser nome também). contudo, ela pode ser 0 e 1 ao mesmo tempo, mais de um rótulo ao mesmo tempo;
- Modelos:
  - Transformação do problema[dados adaptados ao classificador]
    - Binary Relevance
      - faz a classificação separadamente no modo binário

      - Classifier chains
        - parecido com o binary relevance, mas ele usa os multilabel serão utilizados como forma
        gradativa. Tem um desempenho melhor. Ela usa uma variavel independente antiga para uma nova.
        Ex.: 
            Exemplo da musica. A musica pode ser rotulada como agitada e envolvente ao mesmo tempo,
            então o modelo faz assim: classifica as musicas como agitada primeiro, como um problema de classificação
            binária e depois o resultado/relevância do modelo depois do processo é usada agora para classificar
            para o tipo envolvente, ou seja, o resultado de um é usado no outro processo.

      - Label powerset
        - Transforma a combinação de amostra como uma classe.
        Ex.:
            Classe 1 : [1 0 0]
            Classe 2 : [1 1 0]
            Classe 3 : [1 1 1]
        Você transforma o problema de multilabel em um problema de classficação normal como mais uma
        categoria.

  - Algortimos Adaptados[classificador adaptador aos dados]
    - Clare(C4.5);
    - AdaBoost.MH;
    - ML-kNN;

# Métricas de performance de classificação multilabel

- ExactMatch
  - quantas amostras são iguais, 100% a linha do previsto com o real, por isso ser exato.
  - Não é apropiado.

- Hamming Distance ou Hamming Loss
  - Considara os acessos em uma amostra que não foi 100% acertada
  - Usa a distância de hamming para calcular a perda
  - Sempre um valor real entre [0,1]
  - quanto mais próximo de zero, melhor.

** *Data Science* é um processo que você não tem respostas definitivas.