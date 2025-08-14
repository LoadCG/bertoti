# Engenharia de Software I

## 📖 Descrição

Este repositório concentra todas as atividades desenvolvidas durante a disciplina **Engenharia de Software I**.  
Cada atividade será organizada em seções próprias, contendo o enunciado (quando necessário), a execução e eventuais reflexões complementares.

---

# 📝 Atividade 1 — Comentários e Trade-offs

### Objetivo
- Ler dois trechos do livro *Software Engineering at Google* e fazer comentários reflexivos sobre cada um.  
- Explicar três exemplos reais ou hipotéticos de **trade-offs** no contexto de engenharia de software.

---

## 📚 Parte 1 — Comentários sobre *Software Engineering at Google*

### Texto 1 — Percepção da Engenharia de Software

O trecho aborda uma realidade desconfortável: a sociedade tende a considerar outras engenharias mais importantes, pois seus resultados são mais visíveis e tangíveis no mundo real.

> **Reflexão:** Isso cria a expectativa de que a engenharia de software adote métodos tão rigorosos quanto outras áreas, como a engenharia aeronáutica.

Muitas vezes, o engenheiro de software é visto como menos responsável que, por exemplo, um engenheiro de aeronaves.  
Essa visão é equivocada — existem softwares que controlam sistemas críticos e cuidam diretamente de vidas humanas.

---

### Texto 2 — *Programming Over Time*

O trecho reforça a importância de escrever código **escalável** e que permita **evoluir continuamente** ao longo do tempo.  
A meta é que o software não seja apenas funcional no presente, mas que mantenha a capacidade de crescer e se adaptar a novas demandas.

Concordo plenamente com essa visão.  
Acredito que, se empresas de grande porte — como o próprio **Google**, citado explicitamente no texto e no título do livro — adotassem e disseminassem padrões mais rigorosos de engenharia de software, treinando programadores no mundo todo para segui-los, poderíamos alcançar avanços significativos na qualidade e na longevidade dos sistemas.

> **Reflexão:** Escalar código não é apenas uma questão técnica, mas também cultural: exige disciplina, padrões claros e compromisso coletivo.

---

## ⚖ Parte 2 — Três exemplos de *trade-offs* em Engenharia de Software

Um **trade-off** é uma decisão que implica abrir mão de algo para ganhar outra coisa em troca.  
Em engenharia de software, eles aparecem frequentemente quando equilibramos critérios como desempenho, custo, prazo e qualidade.

### 1. Desempenho vs. Manutenibilidade
- **Situação:** Otimizar um algoritmo para rodar extremamente rápido.
- **Ganho:** Melhor tempo de execução e menor consumo de recursos em produção.
- **Perda:** Código mais complexo, difícil de entender e de manter no futuro.  
  → Muitas vezes, é mais viável manter um código levemente mais lento, mas legível e fácil de corrigir.

---

### 2. Velocidade de Entrega vs. Qualidade do Código
- **Situação:** Lançar rapidamente uma nova funcionalidade para atender a uma demanda do cliente.
- **Ganho:** Vantagem competitiva e satisfação imediata do cliente.
- **Perda:** Possível aumento da dívida técnica, exigindo refatorações futuras e gerando riscos de bugs.  
  → O equilíbrio depende do impacto da entrega e do custo da refatoração posterior.

---

### 3. Escalabilidade vs. Custo Inicial
- **Situação:** Projetar um sistema para suportar milhões de usuários desde o início.
- **Ganho:** Infraestrutura preparada para grandes picos de demanda.
- **Perda:** Investimento inicial elevado em servidores, banco de dados e arquitetura complexa que pode não ser necessária no curto prazo.  
  → Em alguns casos, é melhor começar simples e evoluir conforme o crescimento real do produto.

---

## 🔄 Próximos Passos
- Incluir as próximas atividades da disciplina neste repositório, seguindo o mesmo padrão de organização.
- Criar um índice geral para navegação entre atividades.
- Complementar as reflexões com exemplos práticos e estudos de caso.
