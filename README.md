# PulseFlow — Residência em IA (UnB)

**PulseFlow** é um sistema de playlist adaptativa que sugere músicas automaticamente de acordo com o **contexto e a atividade do usuário** (treino, estudo, relaxamento ou trabalho), usando o Spotify Dataset como base e, futuramente, sinais de smartwatch para refinar as recomendações.

Projeto desenvolvido no âmbito da **Residência em Inteligência Artificial** (parceria com a UnB).

---

##  Objetivo

Investigar como características musicais (energia, valência, tempo, dançabilidade etc.) se relacionam com diferentes contextos de atividade, para construir um motor de recomendação que ajuste a playlist automaticamente ao que o usuário está fazendo.

##  Guiding Questions

O projeto é guiado por um conjunto de perguntas norteadoras, organizadas por frente de investigação:

###  Dados
1. Quais os limiares numéricos (quartis, medianas) de *energy* e *speechiness* que definem gêneros focados em relaxamento e estudo?
2. Qual a variância de *loudness* em gêneros acústicos/relaxantes, e que regra pode barrar picos em playlists de Sleep?
3. Que anomalias existem na base de 114 mil faixas (alta *acousticness* + picos de *loudness*) que exigem tratamento prévio?
4. O que separa "focar" de "relaxar"? As features que distinguem os dois estados são as que a intuição prevê?

###  Modelos
1. As *audio features* permitem inferir com separabilidade acústica o contexto de uso da faixa?
2. Todos os erros de classificação de contexto custam o mesmo (assimetria de custo do erro)?
3. Qual o custo relativo de cada tipo de erro — errar para cima no sono é igual a errar para baixo na corrida?
4. Como o modelo deve avaliar a rotina matinal: aumento gradativo de BPM ou evolução conjunta de *valence* + *energy*?
5. Como balancear Precision (não errar o Deep Work) vs. Recall nas métricas de desempenho?

###  Usuários
1. Como o Context Engine resolve a variabilidade inter-usuário (ex: "alta energia" para uma pessoa pode ser barulho estressante para outra)?
2. Quantas vezes por dia uma pessoa troca de contexto de escuta, e ela percebe quando a música "erra o momento"?
3. O que entrevistas/questionários de preferências contextuais com usuários revelam?
4. As preferências musicais mudam de acordo com a atividade que a pessoa realiza?

###  Smartwatch
1. FC (frequência cardíaca) e cadência classificam o estado do usuário com precisão suficiente (detectabilidade do contexto por sensor)?
2. Casar o BPM da música com a cadência do usuário melhora a experiência, ou é folclore?
3. Que sinais um smartwatch comum expõe ao desenvolvedor (frequência de leitura, atraso, custo de bateria)?
4. A combinação entre atividade e sinais do smartwatch pode decidir quando aumentar, manter ou reduzir a intensidade musical?

###  Ética
1. O algoritmo super-recomenda músicas de alta popularidade e cria uma bolha? Como equilibrar com novidade?
2. Otimizar engajamento via perfis rotineiros pode aprisionar o usuário em uma "bolha de filtro"?
3. Coletar FC contínua torna o sistema um tratamento de dado pessoal sensível pela LGPD?
4. Quais dados pessoais e contextuais são realmente necessários para adaptar a música, sem coletar informações desnecessárias ou invasivas?

###  Produção
1. Em quais situações a detecção de conversa próxima deve reduzir automaticamente o volume sem prejudicar a experiência?
2. É melhor treinar um modelo único com a rotina desejada como input, ou usar pipelines independentes por momento?
3. Qual a tolerância comportamental a variações bruscas de volume durante foco extremo?
4. O que já existe no mercado (Spotify, Endel, Weav Run, Apple Fitness+) — o que cada um adapta e a partir de quais sinais?

##  Escopo do MVP

O MVP concentra-se em quatro contextos: **Treino, Estudo, Relaxamento e Trabalho personalizado**.

##  Estrutura do repositório

| Arquivo | Descrição |
|---|---|
| `Análise de Dados do Spotify/` | Notebooks e materiais de exploração do Spotify Dataset |
| `PulseFlow_Notebook.ipynb` | Notebook principal de análise |
| `PulseFlow_Notebook_Corrigido.ipynb` | Versão revisada/corrigida do notebook principal |
| `PulseFlow_Notebook_PF16_Integrado.ipynb` | Notebook com a integração referente à etapa PF16 |
| `PulseFlow_Status_Completo_e_Proximos_Passos.docx` | Status atual do projeto e próximos passos |
| `Relátorio PulseFlow.docx` | Relatório do projeto (Word) |
| `pulseflow-spotify-analytics-relatorio.pdf` | Relatório final em PDF |

##  Como executar

1. Clone o repositório:
   ```bash
   git clone https://github.com/jhessevelyn/PulseFlow---Residencia-IA---UNB.git
   ```
2. Abra os notebooks (`.ipynb`) no Jupyter ou Google Colab.
3. Consulte `PulseFlow_Status_Completo_e_Proximos_Passos.docx` para o status mais recente e os próximos passos planejados.
4. Consulte `Relátorio PulseFlow.docx` ou o PDF equivalente para o relatório completo do projeto.

##  Colaboradores

Projeto feito por Jhessica Evelyn (@jhessevelyn), Breno dos Santos Guimarães (@Br3n0G)), Marjorie Mitzi (@Marjoriemitzi), Pedro Alvim (@PedroAlvimm), e Vitor Gonçalves (@vitorgandrade).

##  Status

Em desenvolvimento — consulte o documento de status para o andamento atualizado das guiding questions e das próximas etapas.
