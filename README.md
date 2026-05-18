# Análise Estrutural de Redes Urbanas: Centro de Ceará-Mirim

## Descrição

Este projeto aplica conceitos avançados de **Estrutura de Dados II** (Hubs e Core Decomposition) para analisar a rede viária urbana do centro de Ceará-Mirim, município do Rio Grande do Norte.

Escolhemos o centro de Ceará-Mirim por ser a região onde os dois membros do projeto residem, permitindo uma análise com maior proximidade com o contexto geográfico estudado.

## Objetivo

Modelar a malha viária como um grafo e identificar:
- **Hubs**: Nós centrais de alta conectividade
- **Estruturas densas**: Através de decomposição k-core
- **Pontos críticos**: Articulações e pontes da rede
- **Propriedades topológicas**: Métricas de centralidade e padrões estruturais

## Ferramentas Utilizadas

- **OSMnx**: Extração de redes do OpenStreetMap
- **NetworkX**: Análise de grafos e métricas de centralidade
- **Gephi**: Visualizações estruturais avançadas
- **GeoPandas & Folium**: Visualizações geográficas
- **Python**: Processamento e análise de dados

## Notebooks

- Localizado em `notebooks/redes_urbanas_ceara_mirim.ipynb`
- Contém código completo para extração, análise e visualização da rede viária

## Conteúdo do Projeto

O projeto é organizado em seções cobrindo:
1. Extração de dados via OSMnx
2. Análise de centralidade e identificação de hubs
3. Decomposição k-core
4. Identificação de componentes críticos
5. Visualizações geográficas e estruturais
6. Interpretação e conclusões

## Questionamentos relevantes da análise:
- Os nós com maior grau coincidem com os nós de maior betweenness?
    
    Na rede viária, os nós com maior grau (número de conexões) nem sempre coincidem com os nós de maior betweenness (nós que atuam como pontes entre diferentes partes da rede). Isso ocorre porque um nó pode ter muitas conexões locais, mas não ser crucial para a conectividade global da rede. Por outro lado, um nó com menos conexões pode ser essencial para conectar diferentes regiões, resultando em alta betweenness.

- O núcleo identificado pelo k-core coincide com os principais hubs?
    Coincide, mas por ser uma região central de uma cidade pequena (k-core maior igual a 2), o núcleo é relativamente pequeno e coincide com os principais hubs, que são os nós mais conectados. No entanto, em redes maiores e mais complexas, o núcleo pode incluir nós que não são necessariamente hubs, mas que são importantes para a estrutura geral da rede.

- O que a métrica de betweenness revela que o grau não revela?
    A métrica de betweenness revela a importância de um nó para a conectividade global da rede, indicando quais nós atuam como pontes entre diferentes partes da rede. O grau, por outro lado, apenas indica o número de conexões locais de um nó, sem considerar sua posição na estrutura geral da rede. Portanto, um nó com alto grau pode não ser tão crucial para a conectividade global quanto um nó com alta betweenness. Como temos uma rede pequena, os nós com maior grau (4) se repetem em vários pontos, mas poucos tem alto betweenness.

- O que muda quando a rede é analisada em sua posição geográfica real e quando é analisada por um layout estrutural?

- Existem regiões críticas para mobilidade urbana na área analisada?
        Sim. A análise revelou que existem regiões críticas para a mobilidade urbana, especialmente em áreas onde há maior concentração de vias e interseções, como o centro da cidade. Esses pontos críticos são identificados por nós com alta betweenness, indicando que eles atuam como pontes entre diferentes partes da rede.

- A rede parece homogênea ou apresenta concentração estrutural?
    A rede apresenta uma concentração estrutural, com alguns nós atuando como hubs e outros nós com alta betweenness que são críticos para a conectividade da rede. A presença de hubs indica que existem áreas com maior conectividade, enquanto a presença de nós com alta betweenness sugere que existem pontos críticos para a mobilidade urbana.

- Os resultados obtidos fazem sentido considerando o conhecimento urbano da região escolhida?
    Sim. Com base na nossa experiência pessoal e conhecimento da região, os resultados obtidos fazem sentido. Os nós identificados como hubs e com alta betweenness correspondem a áreas centrais e de maior fluxo de tráfego, o que é consistente com a estrutura urbana do centro de Ceará-Mirim. A análise geográfica também revelou que as áreas críticas para mobilidade urbana estão localizadas em pontos estratégicos da cidade, onde há maior concentração de vias e interseções. 
    Entendemos também que a rua principal da cidade, que é a General João Varela, por ser duplicada, aparece no grafo com 2 nós por cruzamento, o que pode ter influenciado a análise de centralidade, mas ainda assim os resultados obtidos são coerentes com a realidade urbana da região.

## Autores

- [Lucas Augusto da Silva Cardoso](https://github.com/lucasadasc)
- [Pedro Henrique Ribeiro de Lima](https://github.com/pedenrique3)

Trabalho prático da disciplina **Estrutura de Dados II** (Semanas 5-6) - UFRN

