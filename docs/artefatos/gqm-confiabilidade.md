# Objetivo de Medição 2: Confiabilidade

<div align="center">
    <table border="1" cellspacing="0" cellpadding="8" style="border-collapse: collapse; text-align: left;">
        <tr>
            <th><b>Analisar</b></th>
            <td>o Khan Academy</td>
        </tr>
        <tr>
            <th><b>Para o propósito de</b></th>
            <td>Verificar e entender</td>
        </tr>
        <tr>
            <th><b>Com respeito a</b></th>
            <td>Confiabilidade</td>
        </tr>
        <tr>
            <th><b>Do ponto de vista da</b></th>
            <td>Comunidade de estudantes</td>
        </tr>
        <tr>
            <th><b>No contexto da</b></th>
            <td>Disciplina de Qualidade de Software 1 (FCTE - UnB)</td>
        </tr>
    </table>
</div>

<div align="center">
    <font size="4">
        <figcaption>Tabela 1: Objetivo de Medição: Confiabilidade</figcaption>
    </font>
</div>

-----

### Perguntas e Hipóteses de Medição

**Questão 1: Maturidade**

> Qual é a estabilidade do sistema durante o uso de funções diversas?

- **Hipótese 1.1 (H1.1):** O **Crash Rate (CR)** por sessão de usuário na plataforma (web e mobile) será, em média, inferior a **[0.15%](https://www.alphabin.co/blog/mobile-app-testing-crash-rates)**.
- **Hipótese 1.2 (H1.2):** O **Mean Time Between Failure (MTBF)** do serviço principal será superior a 168 horas de operação contínua antes de uma falha.
    - Não foram encontradas referências que justifiquem as 168h, visto que o ideal o MTBF é ser o mais possível, tendendo até mesmo ao infinito no mundo ideal. Logo, a equipe entendeu que 7 dias (168h) entre falhas para um estudante é aceitável.
    - Sobre MTBF: [Incident management for high-velocity teams ](https://www.atlassian.com/incident-management/kpis/common-metrics)

**Questão 2: Disponibilidade**

> Qual é a disponibilidade do sistema quanto ao acesso e desempenho?

- **Hipótese 2.1 (H2.1):** O **Average Response Time (ART)** para ações críticas do usuário (início de vídeo ou exercício) será, em média, de até **[1 segundo](https://www.headspin.io/blog/how-to-test-application-response-time-for-overall-app-success)**.

**Questão 3: Tolerância a Falhas**

> Qual é o nível de manutenção do funcionamento e preservação de dados quando ocorrem falhas?

- **Hipótese 3.1 (H3.1):** O **Fault Isolation Rate (FIR)** será de, no mínimo, **[92%](https://support.ptc.com/help/wrr/r13.0.0.0/en/wrr/ReferenceGuide/fmea/isolation_percentage.html)** para falhas não-críticas, permitindo que o usuário continue navegando.
- **Hipótese 3.2 (H3.2):** O **Recovery Point Objective (RPO) de Preservação** do progresso do aluno (salvamento de dados) será, no máximo, de **[5 minutos](https://www.veeam.com/blog/recovery-time-recovery-point-objectives.html)**.

**Questão 4: Recuperabilidade**

> Qual é a capacidade do sistema de se recuperar e restaurar dados após falhas?

- **Hipótese 4.1 (H4.1):** O **Recovery Time Objective (RTO)** para restaurar a funcionalidade total do sistema será de, no máximo, **[60 minutos](https://www.veeam.com/blog/recovery-time-recovery-point-objectives.html)**.

-----

### Seleção das Métricas

**Questão 1: Maturidade**

- **Métrica 1.1: Mean Time Between Failure (MTBF)**
    - **Definição:** Tempo médio de operação do sistema entre falhas.
    - **Fórmula:** $MTBF = \frac{Tempo\ Total\ de\ Operação}{Número\ de\ Falhas}$
    - **Coleta:** Automatizada via ferramentas de *Application Performance Monitoring* (APM) ou logs do servidor/aplicação.
    - **Pontuação de Julgamento:**

| **Bom** | **Regular** | **Insatisfatório** |
|:--------:|:-------------:|:-------------------:|
| $\geq 168$ horas | 48 a 167 horas | $< 48$ horas |

- **Métrica 1.2: Crash Rate (CR)**
    - **Definição:** Percentual de sessões de usuário que terminam em *crash*.
    - **Fórmula:** $CR = \frac{Número\ de\ Crashes}{Número\ Total\ de\ Sessões} \times 100\%$
    - **Coleta:** Automatizada via ferramentas de monitoramento de *crash*.
    - **Pontuação de Julgamento:**

| **Bom** | **Regular** | **Insatisfatório** |
|:--------:|:-------------:|:-------------------:|
| $\leq 0.15\%$ | 0.16% a 0.5% | $> 0.5\%$ |

**Questão 2: Disponibilidade**

- **Métrica 2.1: Average Response Time (ART)**
    - **Definição:** Tempo médio de resposta do sistema a requisições críticas.
    - **Fórmula:** $ART = \frac{\sum\ de\ Tempos\ de\ Resposta}{Número\ Total\ de\ Requisições}$
    - **Coleta:** Automatizada via *Real User Monitoring* (RUM).
    - **Pontuação de Julgamento:**

| **Bom** | **Regular** | **Insatisfatório** |
|:--------:|:-------------:|:-------------------:|
| $\leq 1$ segundo | 1.1 a 3 segundos | $> 3$ segundos |

**Questão 3: Tolerância a Falhas**

- **Métrica 3.1: Fault Isolation Rate (FIR)**
    - **Definição:** Avalia a capacidade de isolar a causa raiz de uma falha em um componente.
    - **Fórmula:** $FIR = \frac{Número\ de\ Falhas\ Corretamente\ Isoladas}{Número\ Total\ de\ Falhas\ Detectadas}$
    - **Coleta:** Manual a partir de relatórios de *bug* e logs.
    - **Pontuação de Julgamento:**

| **Bom** | **Regular** | **Insatisfatório** |
|:--------:|:-------------:|:-------------------:|
| $\geq 92\%$ | 90% a 91% | $< 90\%$ |

- **Métrica 3.2: Recovery Point Objective (RPO)**
    - **Definição:** Quantidade máxima de progresso do aluno que pode ser perdida.
    - **Coleta:** Automatizada via logs de transação e replicação de dados.
    - **Pontuação de Julgamento:**

| **Bom** | **Regular** | **Insatisfatório** |
|:--------:|:-------------:|:-------------------:|
| $\leq 5$ minutos | 6 a 15 minutos | $> 15$ minutos |

**Questão 4: Recuperabilidade**

- **Métrica 4.1: Recovery Time Objective (RTO)**
    - **Definição:** Tempo máximo aceitável para restaurar a funcionalidade total.
    - **Coleta:** Manual a partir de logs de incidentes.
    - **Pontuação de Julgamento:**

| **Bom** | **Regular** | **Insatisfatório** |
|:--------:|:-------------:|:-------------------:|
| $\leq 60$ minutos | 61 a 120 minutos | $> 120$ minutos |

-----

### Critérios para Julgamento (Confiabilidade)

- **Aceitável:** $\geq 70\%$ das métricas classificadas como "**Bom**".
- **Parcialmente Aceitável:** Entre $40\%$ e $69\%$ das métricas com nível "**Regular**" ou superior.
- **Inaceitável:** $> 30\%$ das métricas atingindo o nível "**Insatisfatório**".

-----

### Referências

1. [Mobile App Testing Crash Rates](https://www.alphabin.co/blog/mobile-app-testing-crash-rates)
2. [MTBF Metrics - Atlassian](https://www.atlassian.com/incident-management/kpis/common-metrics)
3. [Application Response Time Best Practices](https://www.headspin.io/blog/how-to-test-application-response-time-for-overall-app-success)
4. [Fault Isolation in Systems](https://support.ptc.com/help/wrr/r13.0.0.0/en/wrr/ReferenceGuide/fmea/isolation_percentage.html)
5. [RPO and RTO Concepts - Veeam](https://www.veeam.com/blog/recovery-time-recovery-point-objectives.html)
