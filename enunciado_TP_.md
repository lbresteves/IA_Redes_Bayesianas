# UNIVERSIDADE FEDERAL DE MINAS GERAIS

**DEPARTAMENTO DE ENGENHARIA ELÉTRICA**  
**FUNDAMENTOS DE INTELIGÊNCIA ARTIFICIAL**  
**Trabalho Prático III**  
**Profs. Cristiano Castro e João Pedro Campos**  
_28 de outubro de 2026_

---

## 1. REDES BAYESIANAS

Redes bayesianas são modelos gráficos probabilísticos que representam um conjunto de variáveis aleatórias e suas dependências condicionais por meio de um grafo acíclico dirigido (DAG)[cite: 1]. Cada nó corresponde a uma variável e cada aresta codifica uma relação de dependência direta, enquanto a ausência de arestas expressa independências condicionais[cite: 1]. Associada a cada nó há uma distribuição de probabilidade condicional (CPT), e o produto dessas distribuições fatora a distribuição conjunta de todas as variáveis[cite: 1]. Essa estrutura permite raciocínio sob incerteza de forma compacta e interpretável: dada evidência sobre algumas variáveis, é possível inferir a distribuição de probabilidade das demais[cite: 1].

Neste trabalho, cada grupo irá construir, aprender e interpretar uma rede bayesiana sobre um conjunto de dados de sua escolha, percorrendo o ciclo completo de modelagem: da definição do problema à explicação das decisões do modelo[cite: 1]. Com relação a esse tema, devem ser realizadas as tarefas a seguir[cite: 1].

---

## 2. ESCOLHA DOS DADOS

Cada grupo deve escolher um conjunto de dados tabular para modelar[cite: 1]. O conjunto deve conter, idealmente, menos de 60 variáveis, para manter o aprendizado estrutural e a inferência tratáveis[cite: 1]. Se necessário, podem ser aplicados métodos de seleção de características para eliminar _features_ redundantes e diminuir a dimensionalidade[cite: 1, 2]. Prefira domínios com categorias naturais e alguma estrutura de dependência plausível (por exemplo, dados de saúde, educação ou perfis socioeconômicos), evitando conjuntos puramente contínuos e densamente correlacionados, que tendem a produzir redes densas e de difícil interpretação[cite: 2]. Variáveis contínuas devem ser discretizadas, e o método de discretização apresentado e justificado[cite: 2].

Sugere-se consultar repositórios como o UCI Machine Learning Repository, o Kaggle e o OpenML, bem como bases públicas brasileiras (dados.gov.br, DATASUS, INEP)[cite: 2]. **A escolha do conjunto de dados deve ser previamente aprovada pelos professores para evitar conjuntos triviais ou grandes demais[cite: 2].**

---

## 3. TAREFAS

### Tarefa 1

Descreva o domínio dos dados escolhidos e o pré-processamento realizado (tratamento de valores faltantes, discretização das variáveis contínuas em três faixas por quantis, codificação das categorias)[cite: 2]. Formule ao menos uma pergunta de interesse que a rede bayesiana deveria ser capaz de responder no contexto do problema[cite: 2].

### Tarefa 2

Antes de qualquer aprendizado automático, desenhe manualmente a estrutura da rede que você julga fazer sentido para o domínio, com base no conhecimento sobre as variáveis[cite: 2]. Caso a rede seja grande demais para desenhar, não é necessário montar a rede inteira, foque apenas em algumas relações que você espera encontrar[cite: 2]. Essa estrutura elicitada será comparada com a estrutura aprendida na Tarefa 3[cite: 2].

### Tarefa 3

Aprenda a estrutura da rede a partir dos dados utilizando dois algoritmos: o Hill-Climbing com o score BIC, e qualquer outro método de sua escolha[cite: 2]. O Hill-Climbing está disponível nas principais bibliotecas, e você pode usar qualquer outro método pronto, de bibliotecas ou algum repositório[cite: 2]. Compare as estruturas aprendidas com a estrutura elicitada manualmente na Tarefa 2: onde o algoritmo concordou com a sua intuição? Onde discordou? Discuta possíveis razões para as diferenças[cite: 2].

### Tarefa 4

A partir da estrutura aprendida, estime os parâmetros da rede (as tabelas de probabilidade condicional)[cite: 2]. Normalmente os métodos disponíveis são: máxima verossimilhança e estimação bayesiana com priors[cite: 2]. Utilize o que achar mais pertinente[cite: 2]. Em seguida, utilize a rede para responder às perguntas formuladas na Tarefa 1 por meio de inferência, explorando consultas com diferentes evidências[cite: 2].

### Tarefa 5

Escolha uma predição específica da rede e explique-a usando propriedades da própria rede[cite: 3]. Você pode, por exemplo, fazer uma análise de sensibilidade para descobrir quais variáveis são mais relevantes para aquela predição, usar a topologia da rede para identificar caminhos de influência, produzir contrafactuais (_interventions_) ou analisar o _Markov blanket_[cite: 3]. Use sua criatividade e capacidade de pesquisa para gerar as explicações e interpretar os resultados da rede[cite: 3]. Explicações em linguagem natural também são bem vindas (geração de um texto que explica, em linguagem natural, os detalhes da inferência que a rede fez)[cite: 3].

---

## 4. CONSTRUÇÃO DO RELATÓRIO

Cada grupo deverá entregar um relatório detalhado, preferencialmente escrito em $\LaTeX$, contendo explicações e discussões pertinentes às resoluções de cada tarefa enumerada na seção anterior[cite: 3]. Dentre as discussões que devem constar no documento, estão[cite: 3]:

- Descrição do domínio, das variáveis e do pré-processamento realizado[cite: 3];
- Justificativa da estrutura elicitada manualmente e sua comparação com a estrutura aprendida[cite: 3];
- Explicação básica do algoritmo de aprendizado estrutural e dos métodos de estimação de parâmetros empregados[cite: 3];
- Discussão das respostas obtidas por inferência e da análise de explicabilidade da Tarefa 5[cite: 3].

O relatório será avaliado em termos da clareza da escrita, correção gramatical e riqueza do conteúdo apresentado[cite: 3]. Não hesite em acrescentar imagens, gráficos e tabelas para reforçar sua argumentação[cite: 3]. Lembre-se: figuras e tabelas devem ser devidamente referenciadas no texto[cite: 3]. Todas as referências bibliográficas utilizadas devem constar ao final do documento e estar no mesmo formato (ABNT, APA ou Vancouver, conforme desejarem)[cite: 3].

Recomenda-se o uso da biblioteca `pgmpy` (Python), que cobre aprendizado estrutural, estimação de parâmetros e inferência, além de um notebook reproduzível anexo ao relatório[cite: 3].

---

## 5. USO DE IAS GENERATIVAS

Em tempos de IA generativa, é importante frisar que tais ferramentas podem ser muito úteis e ajudar no aprendizado de conteúdos novos, quando bem utilizadas[cite: 3]. Recomendamos que consultem, caso ainda não o tenham feito, os materiais disponíveis no Moodle sobre o uso ético de IAs no ambiente acadêmico[cite: 3]. **Relatórios que contenham marcas evidentes de uso de IA generativa (como trechos de prompt ou respostas da IA em primeira pessoa) não serão corrigidos[cite: 3, 4].** O uso de IAs é bem-vindo para tarefas que não envolvam geração de conteúdo do zero, mas sim aquelas que auxiliam o pesquisador a tratar, refinar, debugar, corrigir ou melhorar conteúdo já gerado[cite: 4]. Recomendamos fortemente que, caso usem IAs, tomem o cuidado de se certificarem de que estão entendendo o que está sendo feito e não apenas delegando o raciocínio à IA[cite: 4].

**BOM TRABALHO!**[cite: 4]
