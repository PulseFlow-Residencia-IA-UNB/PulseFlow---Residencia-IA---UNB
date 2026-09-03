# PulseFlow — Residência em IA (UnB)

O **PulseFlow** é um sistema de playlist adaptativa que sugere músicas automaticamente de acordo com o **contexto e a atividade do usuário** (treino, estudo, relaxamento ou trabalho), usando o Spotify Dataset como base e, futuramente, sinais de smartwatch para refinar as recomendações. 

Projeto desenvolvido no âmbito da **Residência em Inteligência Artificial** (parceria com a UnB e Instituto Eldorado).

---

##  O Problema e a Solução

* **O Problema (Context Switching):** A sobrecarga cognitiva na seleção contínua de faixas e a ineficiência de playlists estáticas quando o indivíduo transita entre tarefas de alta concentração, relaxamento e atividade motora intensa.
* **A Solução:** Um *Context Engine* preditivo que integra telemetria biométrica (Smartwatch) e atributos acústicos do Spotify Dataset para sintetizar dinamicamente a trilha sonora adequada ao estado mental e corporal do usuário, reduzindo interações manuais.

##  Escopo do MVP e Modos Operacionais

O MVP concentra-se em quatro contextos principais:
1. **Treino (High Energy):** Carga acústica intensa para sincronização neuromuscular (alta energia > 0.80, BPM médio de 129, loudness > -6 dB).
2. **Estudo (Deep Work):** Blindagem cognitiva e eliminação de distrações verbais (speechiness < 0.08, alta instrumentalidade > 0.85).
3. **Relaxamento / Sono:** Desaceleração fisiológica (energia mínima < 0.20, danceability < 0.35, loudness < -12 dB).
4. **Trabalho Personalizado:** Adaptação da trilha ao tipo de trabalho, como programação, design, atendimento ou escritório.

##  Inteligência Analítica e Machine Learning

A investigação técnica revelou descobertas cruciais a partir do processamento do dataset original de 114.000 faixas (reduzido para 89.741 faixas únicas):

* **Modelagem:** O modelo de Machine Learning Random Forest atingiu um F1-Score ponderado de 0.7247, superando a baseline heurística de 0.5488 em +32%.
* **Feature Importance:** As variáveis acústicas mais determinantes para o modelo foram Loudness (19.78%), Acousticness (15.81%) e Instrumentalness (14.88%).
* **Fórmulas Proprietárias:** Criação de métricas heurísticas para engenharia de features, como o **Índice de Distração Cognitiva (CDI)** e o **Score de Calma Acústica (ACS)**.
* **Assimetria de Custo do Erro:** Tocar uma música acelerada durante o sono gera frustração severa (custo altíssimo), enquanto errar o BPM de um treino resulta apenas em um "skip" (custo baixo). O modelo aplica *Cost-Sensitive Learning* para penalizar falsos positivos de alta energia em modos calmos.
* **Ética e LGPD:** O tratamento de dados biométricos (FC) contínuos é um dado sensível. O PulseFlow opera com inferência local (on-device) e exige consentimento explícito, minimizando a coleta de dados.

##  Guiding Questions (CBL)

O desenvolvimento segue o Challenge Based Learning (CBL) e o CRISP-DM, guiado por perguntas norteadoras:

* **Dados:** Quais os limiares numéricos de *energy* e *speechiness* que definem gêneros focados em relaxamento e estudo? O que separa focar de relaxar?
* **Usuários:** As preferências musicais mudam de acordo com a atividade realizada?
* **Modelos:** Como balancear Precision (não errar o Deep Work) vs. Recall? Todos os erros de contexto custam o mesmo?
* **Smartwatch:** A combinação entre atividade e sinais pode decidir mudanças de intensidade musical?
* **Ética:** Otimizar engajamento via perfis rotineiros pode aprisionar o usuário em uma bolha?
* **Produção:** É melhor treinar um modelo único com a rotina como input, ou pipelines independentes?

##  Estrutura do Repositório

| Arquivo | Descrição |
|---|---|
| `Análise de Dados do Spotify/` | Notebooks e materiais de exploração do Spotify Dataset |
| `PulseFlow_Notebook.ipynb` | Notebook principal de análise |
| `PulseFlow_Notebook_Corrigido.ipynb` | Versão revisada/corrigida do notebook principal |
| `PulseFlow_Notebook_PF16_Integrado.ipynb` | Notebook com a integração referente à etapa PF16 |
| `PulseFlow_Status_Completo_e_Proximos_Passos.docx` | Status atual do projeto e próximos passos |
| `Relátorio PulseFlow.docx` | Relatório do projeto (Word) |
| `pulseflow-spotify-analytics-relatorio.pdf` | Relatório final em PDF |

##  Como Executar

1. Clone o repositório:
   ```bash
   git clone [https://github.com/PulseFlow-Residencia-IA-UNB/PulseFlow---Residencia-IA---UNB.git](https://github.com/PulseFlow-Residencia-IA-UNB/PulseFlow---Residencia-IA---UNB.git)

2. Abra os notebooks (`.ipynb`) no Jupyter ou Google Colab.
3. Consulte `PulseFlow_Status_Completo_e_Proximos_Passos.docx` para o status mais recente e os próximos passos planejados.
4. Consulte o PDF equivalente para o relatório completo do projeto.

## Colaboradores

Projeto feito por Jhessica Evelyn (@jhessevelyn), Breno dos Santos Guimarães (@Br3n0G), Marjorie Mitzi (@Marjoriemitzi), Pedro Alvim (@PedroAlvimm) e Vitor Gonçalves (@vitorgandrade).