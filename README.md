# Projeto PLN - Deep Learning

## Cláudia Silva e George Queiroz

## Introdução

O objetivo deste trabalho é realizar análise de sentimentos utilizando técnicas de Processamento de Linguagem Natural (PLN) e Deep Learning para a disciplina de PLN com Deep Learning da Especialização em Deep Learning do CIn/UFPE. 

Para isso, utilizamos Support Vector Machines (SVM) aliadas às abordagens de Bag of Words (BoW) e embeddings, além de empregar o modelo BERT. Coletamos um conjunto de dados obtidos por meio de web scraping no site da Steam, especificamente nos reviews do jogo "Starfield". Este jogo foi escolhido devido à sua grande quantidade de avaliações, tanto positivas quanto negativas. Ao todo, obtivemos **42.651 reviews**, dos quais 33.052 são classificados como positivos e 9.599 como negativos.

## SVM e Bag of Words (BoW)

No primeiro experimento, utilizamos Support Vector Machines (SVM) e a abordagem de Bag of Words (BoW). A abordagem Bag of Words é uma técnica que trata o texto como uma coleção não ordenada de palavras, ignorando a estrutura gramatical e a ordem das palavras. Cada documento de texto é representado como um vetor, onde cada elemento do vetor corresponde a uma palavra do vocabulário. Cada elemento do vetor contém a contagem da ocorrência da palavra no documento.

O SVM é um algoritmo de classificação que busca encontrar a melhor separação entre diferentes classes em um espaço vetorial. Utilizamos o método `CountVectorizer()` para transformar o texto dos reviews em vetores numéricos e o classificador SVM com kernel linear (`SVC(kernel='linear')`).

A escolha do kernel linear se justifica pela natureza da tarefa de análise de sentimentos, em que as palavras-chave que indicam sentimentos positivos ou negativos geralmente são linearmente separáveis. Os resultados obtidos neste experimento demonstraram uma **acurácia de 0.89 e um F1-score de 0.89**.

## SVM e Embeddings

Neste capítulo, exploramos a utilização de embeddings em conjunto com o SVM. Embeddings são representações numéricas de palavras ou frases que capturam informações semânticas e relacionamentos entre palavras. Ao contrário do Bag of Words, os embeddings preservam a ordem das palavras e a semântica.

Utilizamos o método Word2Vec para criar embeddings e testamos o dataset tanto com lematização quanto sem lematização, bem como embeddings de 300 dimensões e 100 dimensões. A lematização não alterou significativamente os resultados dos experimentos.

Com embeddings de 300 dimensões, obtivemos uma acurácia de **0.80 e um F1-score de 0.75**, enquanto com embeddings de 100 dimensões, a **acurácia foi de 0.78 e o F1-score de 0.68**. Esses resultados sugerem que embeddings de maior dimensão podem capturar mais informações semânticas, mas também podem aumentar a dimensionalidade do espaço de características.

## BERT

Por fim, abordamos a utilização do modelo BERT (Bidirectional Encoder Representations from Transformers). O BERT é um modelo de linguagem pré-treinado que atingiu resultados excepcionais em várias tarefas de PLN.

Nos experimentos realizados, treinamos o modelo BERT por 5 épocas e obtivemos um **F1-score de 0.93** para a tafera de análise de sentimentos. No entanto, o custo computacional não permitiu treinar por mais épocas, o que poderia levar a resultados ainda melhores. O BERT se destacou na compreensão de contexto e nuances linguísticas, o que o torna uma escolha poderosa para tarefas de análise de sentimentos.

Em resumo, este projeto explorou várias abordagens de PLN e Deep Learning para a análise de sentimentos em reviews de jogos. Os resultados indicam que oe modelos pré-treinados como o BERT pode melhorar significativamente o desempenho em relação às abordagens tradicionais como Bag of Words e SVM, que por sua vez, obtiveram desempenho satisfatório.

Os experimentos e o pré-processamento do texto estão detalhados nos notebooks.
