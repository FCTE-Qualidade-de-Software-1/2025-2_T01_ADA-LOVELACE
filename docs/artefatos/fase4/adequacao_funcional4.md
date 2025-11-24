##  Relatório de Resultado de Teste

### **Métrica 1.1: Cobertura de Funcionalidades Essenciais**

| Categoria | Detalhe |
| :--- | :--- |
| **Período de Coleta** | 23/11 |
| **Responsável** | Mateus Henrique |
| **Foco da Análise** | Requisitos Funcionais (RF01 a RF016) definidos como essenciais para atender às necessidades dos estudantes (Lucas e Bia). |

---

### **Análise dos Dados Coletados**

A avaliação concentrou-se nos 16 Requisitos Funcionais (RFs) essenciais, verificando se cada um estava Implementado e Operacional (sem falhas críticas) conforme o plano de teste.

* **Total de Requisitos (RFs):** 16
* **RFs Críticos Implementados e Funcionais:** 13
* **RFs Críticos Não Funcionais/Ausentes:** 3 (RF03),(RF11), (RF13)

#### **Cálculo da Métrica (Cobertura de Críticos)**

A cobertura de requisitos implementados e funcionais foi calculada da seguinte forma:

$$\text{Métrica } 1.1 = \frac{\text{Nº de funcionalidades essenciais operacionais}}{\text{Nº total de funcionalidades essenciais esperadas}} \times 100$$
$$\text{Métrica } 1.1 = \frac{\text{13}}{\text{16}} \times 100 = 81.25 $$
---

### **Classificação e Conclusão**

#### **Resultado do Teste: Regular** 

Com um percentual de **81.25%** de cobertura dos requisitos, o resultado da Métrica 1.1 é classificado como **Regular** (faixa de 80%-94%%).

#### **Validação da Hipótese (H1.1)**

A hipótese **H1.1** (Pelo menos 85% das funcionalidades utilizadas pelos estudantes estarão implementadas e operacionais no sistema) é considerada Refutada.

Embora o resultado de 81.25% se enquadre na faixa "Regular", ele está abaixo do limiar de 85% estabelecido na hipótese, indicando que o sistema ainda possui um "débito de funcionalidades" superior ao esperado para atender as necessidades de forma otimizada.

**Conclusão**: O sistema entrega a maior parte do valor essencial, mas falhas na cobertura (falta de 18.75% dos RFs) impedem o alcance do padrão de excelência (Bom) e da meta interna (85%), comprometendo a experiência de usuários com necessidades específicas como certificação ou estudos offline.

---

### **Status dos Requisitos Críticos Avaliados**

| ID   | Requisito a ser Avaliado               | Nível de Importância | Status                           | Observações                                                                                   |
|------|-----------------------------------------|------------------------|------------------------------------|------------------------------------------------------------------------------------------------|
| RF01 | Visualizar aula em vídeo                | Crítico                | Implementado e Funcional           | Vídeo carregado e reproduzido corretamente.                                                   |
| RF02 | Controlar velocidade do vídeo           | Médio                  | Implementado e Funcional           | Controle de velocidade disponível e funcional.                                                |
| RF03 | Acessar aulas offline                   | Alto                   | NÃO Implementado                   | Funcionalidade disponível apenas no aplicativo, não na versão web testada. Compromete a rotina de Bia (estudo em transporte). |
| RF04 | Monitorar progresso do curso            | Médio                  | Implementado e Funcional           | Barra de progresso e lista de aulas concluídas visíveis.                                      |
| RF05 | Retomar de onde parou                   | Crítico                | Implementado e Funcional           | O sistema salva e restaura o ponto exato da última visualização.                              |
| RF06 | Realizar exercícios                     | Crítico                | Implementado e Funcional           | Exercícios interativos são carregados e a submissão funciona.                                 |
| RF07 | Receber feedbacks dos exercícios        | Médio                  | Implementado (Parcialmente Funcional) | Nem todos os exercícios possuem Feedbacks passo a passo. Funcionalidade presente, mas incompleta. |
| RF08 | Submeter atividades                     | Alto                   | Implementado e Funcional           | O sistema possui campos/funcionalidades para submissão de atividades ou respostas complexas.  |
| RF09 | Postar dúvidas                          | Médio                  | Implementado e Funcional           | Seção de comentários/perguntas na página da aula.                                             |
| RF10 | Pesquisar curso específico              | Médio                  | Implementado e Funcional           | Campo de busca é rápido e eficiente.                                                          |
| RF11 | Receber certificação                    | Crítico                | NÃO Implementado                   | O Khan Academy não gera certificação. Falha crítica para Bia (currículo) e para a proposta de valor. |
| RF12 | Realizar simulados                      | Alto                   | Implementado e Funcional           | Simulações para provas específicas estão disponíveis porém em contextos limitados somente ao Paraná e São Paulo que tem cursos específicos.                                         |
| RF13 | Realizar avaliação de nivelamento       | Médio                  | NÃO Implementado                   | Não há teste de nivelamento para iniciar. Dificulta o início de Lucas.                        |
| RF14 | Gamificar experiência do usuário        | Médio                  | Implementado e Funcional           | Elementos de gamificação (pontos, energia, streak semanal, medalhas) estão presentes.                                   |
| RF15 | Acompanhar desempenho geral             | Médio                  | Implementado e Funcional           | Relatórios sobre tempo de estudo disponíveis, aulas assistidas, mas exibidas de forma difícil de se interpretar.                                 |
| RF16 | Transcrição de áudio                    | Médio                  | Implementado e Funcional           | Transcrição disponível nos vídeos (legenda) e transcrição abaixo de cada vídeo aula.                                                  |

---

### **Evidência do Teste**

**Link para o Vídeo do Teste:**

[Vídeo do teste](https://www.youtube.com/watch?v=HoCNmvM4OuA)

### **Métrica 3.1: Relevância dos Requisitos Implementados**

| Categoria | Detalhe |
| :--- | :--- |
| **Período de Coleta** | 24/11/2025 a 28/11/2025 |
| **Responsável** |Pedro Gois |
| **Foco da Análise** | Requisitos Funcionais (RFs) classificados como **Críticos** na Fase 1. |

---

### **Análise dos Dados Coletados**

A avaliação concentrou-se nos 4 requisitos Críticos definidos como essenciais para o fluxo principal do usuário (estudo, prática e reconhecimento).

* **Total de Requisitos Críticos (RFs):** 4
* **RFs Críticos Implementados e Funcionais:** 3
* **RFs Críticos Não Funcionais/Ausentes:** 1 (Gerar Certificação)

#### **Cálculo da Métrica (Cobertura de Críticos)**

A cobertura de requisitos Críticos implementados e funcionais foi calculada da seguinte forma:

$$\text{Cobertura de Críticos} = \frac{3}{4} \times 100 = 75\%$$

---

### **Classificação e Conclusão**

#### **Resultado do Teste: Insatisfatório** 

Com um percentual de **75%** de cobertura dos requisitos Críticos, o resultado da Métrica 3.1 é classificado como **Insatisfatório** (faixa de < 80%).

#### **Validação da Hipótese (H3.1)**

A hipótese **H3.1** (que pressupõe a implementação da maioria dos requisitos Críticos) é considerada **Refutada**.

Embora os requisitos de consumo de conteúdo sejam funcionais, a falha no requisito **"Gerar Certificação"** compromete a etapa final do ciclo de estudo e a proposta de valor de reconhecimento da plataforma.

> **Observação:** A ausência ou falha de um requisito Crítico que impacta a conclusão do fluxo principal (como a certificação) compromete a utilidade e o valor essencial do sistema, exigindo correção de **prioridade máxima**.

---

### **Status dos Requisitos Críticos Avaliados**

| Requisito Crítico | Status | Observações |
| :--- | :--- | :--- |
| **Visualizar Aula em Vídeo** | Implementado e Funcional | Vídeo carregado e reproduzido corretamente em todos os dispositivos. |
| **Recomeçar de Onde o Vídeo Parou** | Implementado e Funcional | O progresso do vídeo foi salvo e restaurado com sucesso. |
| **Realizar Atividades** | Implementado e Funcional | As atividades/exercícios foram carregados e o envio das respostas funcionou sem falhas críticas. |
| **Gerar Certificação** | **NÃO Funcional** | O certificado gerado é apenas motivacional, não sendo reconhecido para capacitação nem horas complementares. |

---

### **Evidência do Teste**

**Link para o Vídeo do Teste:**

[Vídeo do teste](https://www.youtube.com/watch?v=PdgAScXvrPk&t=1s)


---
### **Métrica 2.1: Taxa de sucesso da tarefa**

| Categoria | Detalhe |
| :--- | :--- |
| **Período de Coleta** | 23/11 |
| **Responsável** | Mateus Cavalcante|
| **Foco da Análise** | Análise da implementação e funcionalidade dos requisitos funcionais relacionados à tarefas. |

---

### **Análise dos Dados Coletados**

A avaliação concentrou-se em 7 tarefas comumente realizadas por estudantes, verificando se cada uma estava concluindo da maneira correta conforme o plano de teste.

* **Total de tarefas (RFs):** 7
* **Tarefas concluidas:** 7
* **Tarefas não concluidas:** 0

#### **Cálculo da Métrica (Cobertura de Críticos)**

A cobertura de requisitos implementados e funcionais foi calculada da seguinte forma:

$$\text{Métrica } 2.1 = \frac{\text{Nº de tarefas concluídas corretamente}}{\text{Nº de tarefas iniciadas}} \times 100$$
$$\text{Métrica } 2.1 = \frac{\text{7}}{\text{7}} \times 100 = 100 $$
---

### **Classificação e Conclusão**

#### **Resultado do Teste: Regular** 

Com um percentual de **100%** de tarefas, o resultado da Métrica 2.1 é classificado como **Bom**.

#### **Validação da Hipótese (H1.1)**

A hipótese H2.1 (Pelo menos 90% dos casos de uso para estudantes serão executados corretamente, sem apresentar falhas ou erros) está correta


**Conclusão**: O sistema entrega com maestria as funcionalidades exigidas por estudantes comuns.

**Link para o Vídeo do Teste:**

[Vídeo do teste](https://youtu.be/4h94-PyFvdU)