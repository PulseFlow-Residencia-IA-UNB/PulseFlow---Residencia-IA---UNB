# Investigação e Metodologia

O desenvolvimento é estruturado no método Challenge Based Learning (CBL) integrado ao ciclo de vida de Ciência de Dados (CRISP-DM).

**Objetivos e Escopo**
* **Objetivo de negócio:** Aumentar a adequação da experiência musical ao contexto atual e reduzir as interações manuais e skips.
* **Objetivo de ML:** Classificar músicas de acordo com sua adequação aos contextos, utilizando Macro F1 para classificação e Precision@10 para ranking.
* O sistema **TRATA** a recomendação musical baseada no Spotify Dataset e dados de contexto do usuário.
* O sistema **NÃO TRATA** diagnósticos médicos, automação clínica em ambientes críticos, ou recomendação colaborativa entre diferentes usuários.

**Guiding Questions (Matriz de Priorização)**
* **Responder JÁ (Alto Impacto / Fácil):** Identificar características musicais por modo (GQ1), investigar mudanças de preferência por atividade (GQ2) e variações no perfil de trabalho (GQ3).
* **Planejar (Alto Impacto / Difícil):** Integração com smartwatch (GQ4) e avaliação do modelo vs. seleção aleatória (GQ6).
* **Se sobrar tempo:** Limites éticos de coleta de dados (GQ7).
* **Cortar sem dó:** Detecção de conversa no ambiente para redução de volume (GQ5).

**Governança e LGPD**
* A coleta de telemetria (frequência cardíaca) é classificada como tratamento de dados pessoais sensíveis pelo Artigo 5º da LGPD.
* A pesquisa com usuários indicou que 79.5% dos respondentes não se sentem desconfortáveis em compartilhar esses sinais para essa finalidade específica.
* O sistema opera com inferência processada localmente (Edge/Mobile) e exige consentimento explícito, sem armazenamento contínuo na nuvem.