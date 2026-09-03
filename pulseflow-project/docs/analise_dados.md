# Inteligência Analítica (EDA)

A análise foi conduzida sobre o Spotify Tracks Dataset, composto inicialmente por 114.000 registros balanceados em 114 gêneros. Após a limpeza e deduplicação, a base útil resultou em 89.741 faixas únicas. 

**Diagnóstico Geral do Catálogo**
* A popularidade média do dataset é de 33.2.
* Os gêneros líderes em popularidade são pop-film, k-pop e chill.
* O modo musical "Maior" domina a composição do catálogo, correspondendo a 63.7% das faixas (57,2 mil).
* O bucket de duração ideal no catálogo se concentra entre 3 e 4 minutos, com popularidade média de 34.9.
* Anomalias acústicas foram tratadas via Hard Filters: foram isoladas 41 faixas no gênero `sleep` com compressão agressiva (loudness > -10 dB).

**Feature Engineering: Fórmulas PulseFlow**
* **Índice de Distração Cognitiva (CDI):** Calculado como `Speechiness × (1 - Instrumentalness) × Loudness`. A métrica blinda tarefas lógicas limitando o CDI a menos de 0.015.
* **Score de Calma Acústica (ACS):** Medido por `Acousticness × (1 - Energy) × (1 - Danceability)`.

**Descobertas e Resultados de ML**
* A intuição falha ao presumir a instrumentalidade como o único divisor entre Foco e Sono; ambos os modos possuem medianas instrumentais elevadas (> 0.87). A separabilidade real depende da pressão sonora (loudness) e da cadência rítmica (danceability).
* A densidade de BPM no modo Treino concentra-se em 128 BPM, permitindo sincronização exata com o smartwatch (Zonas aeróbicas 3 e 4).
* O classificador Random Forest atingiu um F1-Score ponderado de 0.7247, superando a baseline heurística (0.5488).
* As features com maior Gini Importance foram Loudness (19.78%), Acousticness (15.81%) e Instrumentalness (14.88%).
* A análise comprovou uma severa assimetria no custo do erro: prever acidentalmente uma faixa intensa de treino durante o sono causa rejeição imediata, exigindo penalidades de Cost-Sensitive Learning na função de perda.