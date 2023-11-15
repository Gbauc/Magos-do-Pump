# Trabalho final de Aprendizado de Máquina

Autores: Emelyn Alves, Geovana Bettero, Gustavo Uchôa, Samira Oliveira.

## Quem somos? 
Olá! Nós somos os Magos-do-Pump, grupo da disciplina de Aprendizado de Máquina formado por alunos do 2° semestre de Bacharelado em Ciência e Tecnologia da Ilum - Escola de Ciência. 

## Objetivo: 
Prever, por meio de modelos treinados por aprendizado de máquina, se uma pessoa é ou não fumante ou alcoólatra, com base em dados de seus sinais corporais. 

## Metodologia:
Utilizamos o dataset "Smoking and Drinking Dataset with body signal" para treinar os seguintes modelos do scikit-learn: Dummy Classifier, KNN Classificador, Regressão Logística e Floresta Aleatória. 

## Descrição do dataset: 
["Smoking and Drinking Dataset with body signal"](https://www.kaggle.com/datasets/sooyoungher/smoking-drinking-dataset) é um conjunto de dados coletados do Seguro de Saúde Nacional da Coreia do Sul, disponível na plataforma [kaggle](https://www.kaggle.com/). Esse dataset é, originalmente, formado por 24 atributos/colunas e 284428 exemplos/linhas. Os atributos e suas classificações (categórico ou numérico) são: 
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

Para o trabalho os atributos escolhidos para serem targets foram: 23 e 24. 

