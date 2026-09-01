# Visão de Produto e UX

O PulseFlow foi desenhado para atuar de forma invisível, adaptando-se às necessidades fisiológicas e mentais do usuário.

### Os 4 Modos Operacionais
1. **Treino:** Mais energia e motivação (Foco em *Energy* e *Tempo*).
2. **Estudo:** Mais foco e concentração (Blindagem cognitiva contra vocais).
3. **Relaxamento / Sono:** Mais calma e bem-estar (Sanitização de picos acústicos).
4. **Trabalho Personalizado:** Subdividido em Programação, Design, Escritório e Atendimento.

### Personas e Casos de Uso
* **Estudante Universitário:** Sai de um treino de crossfit e entra no carro para a faculdade. O sistema detecta o deslocamento e troca a reprodução para um podcast ou música lo-fi, sem intervenção manual.
* **Desenvolvedora de Software:** Precisa de raciocínio lógico profundo. O modo *Trabalho - Programação* entra em ação com alta instrumentalidade e batidas cadenciadas, bloqueando letras que ativariam o centro de linguagem do cérebro.
* **Cirurgião Cardíaco:** Em ambientes críticos, a localização não é sinal suficiente. O PulseFlow solicita uma confirmação rápida e congela o perfil sonoro para garantir estabilidade absoluta durante o procedimento.

### O "Context Engine" e Lógica de Automação
O núcleo de tomada de decisão segue um pipeline de 6 etapas:
1. **Detectar Contexto:** Atividade, horário, wearable ou rotina.
2. **Estimar Confiança:** 
   * *Alta:* Ativação automática.
   * *Média:* Pede confirmação (Micro-Feedback).
   * *Baixa:* Mantém o estado atual.
3. **Consultar Perfil:** Recuperar o que funciona para o usuário específico.
4. **Ranquear Conteúdo:** Cruzamento com o Spotify Dataset.
5. **Adaptar Reprodução:** Transição via API.
6. **Aprender com Feedback:** Cliques de "pular" ou salvamentos.