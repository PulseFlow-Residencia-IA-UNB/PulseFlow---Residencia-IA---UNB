# Planejamento, Canvas e Investigação (CBL)

Baseado na metodologia *Challenge Based Learning*, o desenvolvimento foi norteado pela definição estrita do problema e levantamento de evidências. Gestão de backlog e design foram conduzidos via Jira e Miro.

### Escopo (TRATA / NÃO TRATA)
* **O SISTEMA TRATA:** Seleção contínua de faixas pré-indexadas por características acústicas; adaptação para contextos de escuta inferidos por biometria (smartwatch); reprodução via Spotify Premium.
* **O SISTEMA NÃO TRATA:** Geração de áudio por IA; recomendação colaborativa entre usuários (não expande o gosto, apenas reordena o conhecido); automação clínica; inferência de humor sem contexto; usuários sem wearable.

### Guiding Questions (Matriz de Priorização)

**🟢 Responder JÁ (Must Have - Alto Impacto / Fácil)**
1. **Dados:** Quais limiares numéricos (quartis, medianas) definem gêneros focados em relaxamento e estudo?
2. **Modelo:** O dataset não tem exercício rotulado. Que proxy usar e como validar?
3. **Usuário:** Como o motor resolve a variabilidade inter-usuário (ex: o que é alta energia para um, é barulho para outro)?

**🟡 Planejar (Should Have - Alto Impacto / Difícil)**
4. **Smartwatch:** Sinais de frequência cardíaca e cadência podem ajudar a decidir quando alterar a intensidade da música?
5. **Modelo:** Como balancear as métricas de Precision (não errar no Deep Work) vs Recall?

**🔵 Se Sobrar Tempo (Could Have - Baixo Impacto / Fácil)**
6. **Ética:** Quais dados são realmente necessários para personalizar a música sem invadir a privacidade (LGPD)?

**🔴 Cortar Sem Dó (Won't Have - Baixo Impacto / Difícil)**
7. **Ambiente:** Em quais situações a detecção de conversa próxima deve reduzir o volume sem atrapalhar a experiência? (Complexidade de UX/Permissões alta para o MVP).