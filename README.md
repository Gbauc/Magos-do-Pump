# Trabalho final de Aprendizado de Máquina

_Autores:_ Emelyn Alves, Geovana Bettero, Gustavo Uchôa, Samira Oliveira.

## Quem somos? 
Olá, querido leitor! Nós somos os Magos-do-Pump, grupo da disciplina de Aprendizado de Máquina formado por alunos do 2° semestre de Bacharelado em Ciência e Tecnologia da Ilum - Escola de Ciência, escola de ensino superior do CNPEM (Centro Nacional de Pesquisa em Energia e Materiais). O grupo é fruto da "fusão" de duas duplas: Phosphorus do Python (Emelyn e Gustavo) e Grahcyanne's (Geovana e Samira). 

## Objetivo: 
Prever, por meio de modelos treinados por aprendizado de máquina, se uma pessoa é ou não alcoólatra, com base em dados de seus sinais corporais. 

## Metodologia:
Utilizamos o dataset "Smoking and Drinking Dataset with body signal" para treinar os seguintes modelos do `scikit-learn`: Dummy Classifier, KNN Classificador, Regressão Logística, Árvore de Decisão e Floresta Aleatória. Foram utilizadas, para tratamento dos dados e criação dos modelos as seguintes bibliotecas: `sklearn`, `numpy`, `pandas`, `seaborn`, `imblearn`, `pickle` e `matplotlib`. Além disso, contamos também com a ajuda do Heisenberg, o HPC (Computador de Alto Processamento) da Ilum, para processar os dados e executar o modelo de Floresta Aleatória mais eficientemente. 

## Sobre o dataset: 
["Smoking and Drinking Dataset with body signal"](https://www.kaggle.com/datasets/sooyoungher/smoking-drinking-dataset) é um conjunto de dados coletados do Seguro de Saúde Nacional da Coreia do Sul, disponível na plataforma [kaggle](https://www.kaggle.com/). Esse dataset utilizado é formado por 24 atributos/colunas e 284429 exemplos/linhas. Os atributos e suas classificações (categórico ou numérico) são: 
1. `sex` - Sexo (feminino ou maculino); categórico (C)
2. `age` - Idade; numérico (N)
3. `height` - Altura (cm); N
4. `weight` - Massa (kg); N
5. `waistline` - Circunferência abdominal (cm); N
6. `sight_left` - Visão do olho esquerdo; N
7. `sight_right` - Visão do olho direito; N
8. `hear_left` - Audição do ouvido esquerdo (1. audição normal; 2. audição anormal); C
9. `hear_right` - Audição do ouvido direito (1. audição normal; 2. audição anormal); C
10. `SBP` - Pressão sanguínea sistólica (mmHg); N 
11. `DBP` - Pressão sanguínea diastólica (mmHg); N 
12. `BLDS` - Glicemia em jejum (mg/dL); N 
13. `tot_chole` - Colesterol total (mg/dL); N
14. `HDL_chole` - Colesterol HDL (mg/dL); N
15. `LDL_chole` - Colesterol LDL (mg/dL); N
16. `triglyceride` - Triglicerídeos (mg/dL); N
17. `hemoglobin` - Hemoglobina (g/dL); N
18. `urine_protein` - Proteína na urina (1(-), 2(+/-), 3(+1), 4(+2), 5(+3), 6(+4)); C 
19. `serum_creatinine` - Creatinina no sangue (mg/dL); N
20. `SGOT_AST` - Enzima aspartato aminotransferase (IU/L); N
21. `gamma_GTP` - Enzima gama glutamil transferase (IU/L); N
23. `SMK_stat_type_cd` - Estado de fumante (1. nunca fumou; 2. costumava fumar, mas parou; 3. fuma); C
24. `DRK_YN` - Estado de alcoólatra (Y - sim; N - não); C

Para o trabalho os atributos escolhidos para ser o target foi o 23. 
*Lembrando:* Targets são os atributos de um conjuntos de dados que queremos prever.

## Sobre o scikit-learn e os modelos utilizados: 
O `scikit-learn` ou `sklearn` é uma biblioteca de código aberto, em linguagem Python, que oferece ferramentas para análise preditiva de dados a partir de aprendizado de máquina. O sklearn permite a aplicação de diversos modelos, já conhecidos matematicamente, para ajustar e prever dados. Nesse trabalho utilizamos 4 dos modelos disponibilizados pelo sklearn, vamos explorá-los? 

1. Dummy Classifier (`sklearn.dummy.DummyClassifier`): é um classificador fictício que realiza previsões que ignoram os recursos de entrada, ou seja, faz previsões sem a procura de padrões, a fim de medir a performance básica do modelo e poder compará-la com outros classificadores mais complexos, como a Floresta Aleatória. Portanto, usamos essa ferramenta para ter uma noção do desempenho base do modelo [1]. 
  
2. KNN Classificador (`sklearn.neighbors.KNeighboursClassifier`): é um classificador que realiza previsões baseadas nas distâncias (eucliadiana; distância entre pontos) em relação aos dados vizinhos mais próximos. Assim, supondo que dos 5 vizinhos mais próximos de um dado x 3 são azuis e 2 vermelhos, então o dado x será previsto como vermelho, já que a maioria de seus vizinhos mais próximos são dessa cor, como mostra a imagem abaixo:

![image](https://github.com/Gbauc/Magos-do-Pump/assets/135053736/e157db63-cef4-4c88-ad3e-1d494e449a1a) [1]

É importante ressaltar que, para o classificador KNN: 1. é possível mudar o número de k, que corresponde aos vizinhos mais próximos, para `sk.learn` o padrão de vizinhos é 5; 2. e que o número de k deve ser não tão pequeno, para que não ocorra um sobreajuste do modelo, nem tão grande, para não haver um subajuste.
   
3. Regressão Logística (`sklearn.linear_model.LogisticRegression`): é um modelo estatítico que estima a probabilidade de ocorrência de um evento, a partir de variáveis independentes de um dataset. A variável resultante ou dependente da regressão logística assume valores boobleanos, ou seja, 0 ou 1. A regressão logística é usada para entender a relação entre as variáveis independentes e dependentes e, por ser um modelo discriminativo, consegue distinguir classes e categorias, sendo eficiente para utilizar em datasets com dados categóricos. 

4. Árvore de decisão (`sklearn.tree.DecisionTreeClassifier`): é uma ferramenta de classificação e regressão usadas para prever o valor de um target a partir de regras simples de decisão, ou seja, condições oriundas do dataset. Uma das grandes vantagens desse modelo é o fato dele ser visual! Abaixo temos um exemplo de árvore de decisão: 

![image](https://github.com/Gbauc/Magos-do-Pump/assets/135053736/c6cca03c-3e8a-4029-baa3-ac4e4212bf05)[2]

5. Floresta Aleatória (`sklearn.emsemble.RandomForestClassifier`): é um classificador versátil, resolve problemas de classificação e de regressão, que preve um dado a partir da criação aleatória de diversas árvores de decisão.
   
>> OBS: A floresta é _muito custosa computacionalmente_! Se estiver rodando o código disponível no repositório em um computador convencional, não se assuste se esse modelo demorar muito tempo para executar, é normal! :)  

## Sobre o repositório: 
O Notebook com os códigos feitos pelo grupo está no arquivo `TrabalhoFinal.ipynb`, em jupyter notebook. E o dataset está em um arquivo .cvs, nomeado: `smoking_dataset_deus.csv`.

### Referências: 
[1] (https://scikit-learn.org/stable/)https://scikit-learn.org/stable/)

### Imagens: 
[1] (https://didatica.tech/o-que-e-e-como-funciona-o-algoritmo-knn/)

[2] https://brains.dev/2023/pratica-arvores-de-decisao/
