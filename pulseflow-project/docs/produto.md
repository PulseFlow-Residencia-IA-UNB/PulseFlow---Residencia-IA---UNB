# Visão de Produto e UX

O conceito central do PulseFlow resolve o problema de "Context Switching", que ocorre quando o usuário muda de contexto, mas o serviço de streaming pode continuar no conteúdo do contexto anterior[cite: 16]. O sistema reconhece mudanças de contexto e adapta a experiência de reprodução ao perfil do momento, reduzindo interações desnecessárias.

**Modos Operacionais**
* **Treino (High Energy):** Foco em alta energia (> 0.80), BPM médio de 129 e loudness superior a -6 dB para sincronização neuromuscular.
* **Estudo (Deep Work):** Blindagem cognitiva com speechiness restrita (abaixo de 0.08) e alta instrumentalidade (> 0.85).
* **Relaxamento / Sono:** Desaceleração fisiológica com energia mínima (< 0.20) e ausência de picos dinâmicos (loudness < -12 dB).
* **Trabalho Personalizado:** Adaptado ao tipo de atividade, como Programação (CDI < 0.015), Design ou Escritório.

**Personas e Casos de Uso**
* **Estudante em deslocamento:** Reduz a interação manual no trânsito ativando perfis habituais (como podcasts) ao identificar a saída de um treino para a direção.
* **Cirurgião cardíaco:** Em ambientes críticos, solicita confirmação rápida e mantém a estabilidade musical, evitando alterações automáticas inesperadas.
* **Desenvolvedora de software:** Prioriza baixa speechiness e energia moderada para tarefas de raciocínio profundo.

**O Context Engine**
1. **Detectar contexto:** Através de atividade, horário ou modo escolhido.
2. **Estimar confiança:** Confiança alta altera automaticamente; confiança média pede confirmação.
3. **Consultar perfil:** Recupera o que funciona para o usuário naquele cenário.
4. **Ranquear conteúdo:** Seleciona faixas usando as características musicais e preferências.
5. **Adaptar reprodução e aprender:** Executa a transição e calibra o sistema via feedback implícito (skips e curtidas).