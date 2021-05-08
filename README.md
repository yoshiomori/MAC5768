## Enunciados e discussão dos EPs
**Datas de entrega:**

EP1: 13/05

EP2: 15/06

EP3: 29/07



**Material de entrega:**

Material de entrega no eDisciplinas: apenas o JN .ipynb
Material disponível com link indicado no JN: git do projeto + dados


**EP1**

Os estudantes devem se organizar em grupos de até 3 participantes. 

No EP1, os estudantes devem coletar uma base de imagens de objetos de sua casa (por exemplo, garfos, facas, poltronas, celulares, roupas, pets). A base de imagens será formada a partir de fotos de objetos tiradas na sua casa. Vamos montar uma base de imagens a ser usadas nos EPs 2 e 3. A base de imagens deve ter fotos com as seguintes características:

 - 10 classes 
 - mínimo de 3 e máximo de 10 objetos por classe
 - 3 variações de fundo por objeto
 - 4 variações de iluminação por objeto com os produtos cartesianos: {dentro de casa, fora de casa} X {de dia, de noite}
 - 3 repetições para cada situação acima

O EP1 consiste em:

1. Formar a base de imagens
2. Organizar a base em diretórios: Dados + Metadados. Metadados podem ser representados de 3 maneiras: 1- nome do arquivo; 2- arquivo txt com o mesmo nome do arquivo da img; 3- CSV com metadados.
3. Criar um jupyter notebook para ler a base, publicar uma Tabela Sumária dos Dados e visualizar a base usando funções MNIST-like
Criar um projeto no github para seus EPs 1, 2, 3 e colocar o material do EP1 lá.
4. Observações sobre a Tabela Sumária dos Dados: 

===================================

**Tabela Global Sumária**

Descrição | Valor (Cabeçalho da Tabela)


Número de classes | 10

Número de imagens | XXXXX

Tamanho da base (bytes) | XXXXX MB

Resolução das imagens | XXXX linhas por YYYY colunas

=================================

**Tabela detalhada por classe**

Nome do objeto | características das amostras

Faca |  4 objetos | 3 variações de fundo (com descrição) | 4 variações de iluminação (com descrição) | número de repetições | total de amostras 

==============================

**EP2**

O EP2 consiste em criar dois JN para resolver duas tarefas importantes de visão computacional:

**EP2.1: Data augmentation**

Cada grupo deve criar um JN contendo funções para fazer data augmentation do dataset do EP1. Mais informações sobre Data Augmentation são encontradas aqui:

https://github.com/aleju/imgaug

https://www.kaggle.com/parulpandey/overview-of-popular-image-augmentation-packages

As funções de data augmentation serão aplicadas a imagens em níveis de cinza. Portanto, o dataset original precisará ser convertido para níveis de cinza. Deve-se criar 5 funções de data augmentation. Cada função será aplicada a cada imagem do dataset do EP1. Assim, o **augmentedDataset** terá 5X o tamanho do original. Cada grupo deve implementar as seguintes funções de data augmentation:

1. RGB2gray (ie converter as imagens RGB originais em níveis de cinza)
2. Soma de fundo com gradiente de níveis de cinza
3. Logaritmo da imagem
4. Exponencial da imagem
5. Filtro da média implementado usando convolução

Deve-se usar as funções do EP1 para visualização dos resultados do augmentedDataSet.

**EP2.2: Normalização e análise da variação das classes**

Deve-se criar um JN que realize a normalização das imagens de cada classe do augmentedDataSet. Deve-se usar a equalização de histogramas como função inicial de normalização, gerando um **normalizedDataset**. As funções de análise de cada classe abaixo devem ser aplicadas ao **originalGrayDataset, augmentedDataset e normalizedDataset**. Assim, esse JN deve calcular e mostrar para cada dataset:

1. Protótipo médio de cada classe
2. Histograma médio de cada classe
3. Variância do histograma de cada classe


**EP3**

O EP3 tem dois objetivos principais: 



3.1- Segmentação do objeto de interesse: O objetivo desta etapa é segmentar o  objeto do fundo, produzindo uma imagem binária: 0 para o fundo e 1 para o objeto. Dois tipos de segmentação serão usados: manual, para geração do ground-truth, e automática usando algum algoritmo de sua escolha. Exemplo de ground-truth:



![1](https://i.postimg.cc/rpbqQdgz/Whats-App-Image-2020-11-24-at-14-00-11.jpg)



O ground-truth deve ser gerado para pelo menos 15% das amostras de cada classe. 



3.2- Classificação do objeto de interesse. Esses dois objetivos devem ser organizados em 2 seções diferentes ou dois JN diferentes. 



As etapas do EP3 estão descritas no vídeo da aula e na figura abaixo. Tanto 3.1 e 3.2 devem produzir relatórios de performance dos algoritmos de segmentação e de classificação, respectivamente.



![2](https://i.postimg.cc/9M7CSWNb/Captura-de-Tela-2020-11-24-a-s-15-03-23.png)



Pipelines das partes 1 e 2 do EP3: 


![3](https://i.postimg.cc/Zq0T8P81/EP3-pipeline-Page-1.png)

![4](https://i.postimg.cc/GmXLTgyF/EP3-pipeline-Page-2.png)


