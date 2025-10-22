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
    - O Khan Academy apresenta uma média de 4.5 estrelas nas plataformas e, de acordo com [Pratik Patel](https://www.alphabin.co/blog/mobile-app-testing-crash-rates), tais aplicações apresentam $CR = ~00.15%$.
- **Hipótese 1.2 (H1.2):** O **Mean Time Between Failure (MTBF)** do serviço principal será superior a 30 horas de operação contínua antes de uma falha.
    - Não foram encontradas referências que justifiquem as 30h, visto que o ideal o MTBF é ser o maior possível, tendendo até mesmo ao infinito no mundo ideal. Logo, a equipe entendeu 30h entre falhas para um estudante é aceitável, tendo em vista que o mesmo utilizará o sistema por no máximo 4 horas diárias.
    - Sobre MTBF: [Incident management for high-velocity teams](https://www.atlassian.com/incident-management/kpis/common-metrics)

**Questão 2: Disponibilidade**

> Qual é a disponibilidade do sistema quanto ao acesso e desempenho?

- **Hipótese 2.1 (H2.1):** O **Average Response Time (ART)** para ações críticas do usuário (início de vídeo ou exercício) será, em média, de até **[1 segundo](https://www.headspin.io/blog/how-to-test-application-response-time-for-overall-app-success)**.
- **Hipótese 2.2 (H2.2):** O **Availability Percentage** para o sistema deverá ser maior ou igual a **[99%](https://www.penguinsolutions.com/en-us/resources/blog/rule-nines-availability-always-on-world)**, ou seja, o mesmo não deve ficar fora do ar por mais que 87.6 horas ao ano.
    - Apesar de não encontramos uma recomendação direta de qual seria o *Availability Percentage* ideal para sistemas de educação como o Khan Academy, for entendido a partir de pesquisas, que 99% é o padrão de qualidade do mercado para sistemas de software em geral.

**Questão 3: Tolerância a Falhas**

> Qual é a capacidade do sistema de isolar falhas e continuar operando?”

- **Hipótese 3.1 (H3.1):** O **Fault Isolation Rate (FIR)** será de, no mínimo, **[90%](https://support.ptc.com/help/wrr/r13.0.0.0/en/wrr/ReferenceGuide/fmea/isolation_percentage.html)** para falhas não-críticas, permitindo que o usuário continue navegando.

- **Hipótese 3.2 (H3.2):** O **Recovery Point Objective (RPO)** será de, no máximo, **[5 minutos](https://www.headspin.io/blog/how-to-test-application-response-time-for-overall-app-success)**, garantindo que a perda de dados ou progresso do aluno em caso de falha seja mínima e aceitável.

**Questão 4: Recuperabilidade**

> Qual é a capacidade do sistema de se recuperar e restaurar dados após falhas?

- **Hipótese 3.2 (H3.2):** O **Recovery Point Objective (RPO) de Preservação** do progresso do aluno (salvamento de dados) será, no máximo, de **[5 minutos](https://aws.amazon.com/blogs/mt/establishing-rpo-and-rto-targets-for-cloud-applications/)**.
- **Hipótese 4.1 (H4.1):** O **Recovery Time Objective (RTO)** para restaurar a funcionalidade total do sistema será de, no máximo, **[5 minutos](https://aws.amazon.com/blogs/mt/establishing-rpo-and-rto-targets-for-cloud-applications/)**.

-----

### Seleção das Métricas

**Questão 1: Maturidade**

- **Métrica 1.1: Mean Time Between Failure (MTBF)**
    - **Definição:** Tempo médio de operação do sistema entre falhas.
    - **Fórmula:** $MTBF = \frac{Tempo\ Total\ de\ Operação}{Número\ de\ Falhas}$
    - **Coleta:**
        - Os membros da equipe serão responsáveis por testar a aplicação durante 1 semana.
        - Cada membro deverá registrar os falhas encontradas e o tempo toral de uso.
        - Após isso vamos realizar o cálculo por meio da média.
    - **Pontuação de Julgamento:**

| **Bom** | **Regular** | **Insatisfatório** |
|:--------:|:-------------:|:-------------------:|
| $\geq 30$ horas | 30 a 29 horas | $< 30$ horas |

- **Métrica 1.2: Crash Rate (CR)**
    - **Definição:** Percentual de sessões de usuário que terminam em *crash*.
    - **Fórmula:** $CR = \frac{Número\ de\ Crashes}{Número\ Total\ de\ Sessões} \times 100\%$
    - **Coleta:**
        - Todos os membros da equipe vão testar a aplicação durante 2 semanas.
        - Serão registrados os casos de `crash`, ou seja, quando o sistema ficou inutilizável e foi necessário recarregamento.
    - **Pontuação de Julgamento:**

| **Bom** | **Regular** | **Insatisfatório** |
|:--------:|:-------------:|:-------------------:|
| $\leq 0.15\%$ | 0.16% a 0.5% | $> 0.5\%$ |

**Questão 2: Disponibilidade**

- **Métrica 2.1: Average Response Time (ART)**
    - **Definição:** Tempo médio de resposta do sistema a requisições críticas.
    - **Fórmula:** $ART = \frac{\sum\ de\ Tempos\ de\ Resposta}{Número\ Total\ de\ Requisições}$
    - **Coleta:**
        - Automatizado, vamos deixar um computador realizando requisições para o sistema de forma periódica.
        - Após uma coletar entre 500 e 800 requisições o valor será calculado.
    - **Pontuação de Julgamento:**

| **Bom** | **Regular** | **Insatisfatório** |
|:--------:|:-------------:|:-------------------:|
| $\leq 1$ segundo | 1.1 a 3 segundos | $> 3$ segundos |

- **Métrica 2.2: Availability Percentage**
    - **Definição:** Quanto tempo do total um sistema está operacional e pronto para uso.
    - **Fórmula:** $AP = \frac{Total\ Available\ Time}{Total\ Possible\ Time \times 100}$
    - **Coleta:**
        - Será realizada uma pesquisa para saber se nos últimos anos houve uma queda do Khan Academy.
        - Além disso, vamos deixar um servidor realizando `pings` periódicos ao Khan Academy durante 2 semanas.
    - **Pontuação de Julgamento:**

| **Bom** | **Regular** | **Insatisfatório** |
|:--------:|:-------------:|:-------------------:|
| $\ge 99\%$ | $99\%$ a $98\%$ | $\lt 98\%$  |

**Questão 3: Tolerância a Falhas**

- **Métrica 3.1: Fault Isolation Rate (FIR)**
    - **Definição:** Avalia a capacidade de isolar a causa raiz de uma falha em um componente.
    - **Fórmula:** $FIR = \frac{Número\ de\ Falhas\ Corretamente\ Isoladas}{Número\ Total\ de\ Falhas\ Detectadas}$
    - **Coleta:** Manual a partir de logs e métricas de observabilidade (ex: error tracing, health checks, monitoramento de containers).
    - **Pontuação de Julgamento:**

| **Bom** | **Regular** | **Insatisfatório** |
|:--------:|:-------------:|:-------------------:|
| $ < 92\%$ | 90% a 94% | $ > 90\%$ |


**Justificativa:**
O Fault Isolation Rate é fundamental para medir a resiliência operacional do sistema. Um alto FIR indica que o sistema consegue isolar falhas localizadas, evitando que problemas em um módulo afetem o restante da aplicação — característica essencial em ambientes com alta disponibilidade, como plataformas educacionais online.

**Propósito** Identificar fragilidades de arquitetura e pontos de acoplamento excessivo

- **Métrica 3.2: Recovery Point Objective (RPO)**
    - **Definição:** Tempo máximo aceitável entre o último ponto de salvamento consistente e o momento de uma falha.
    - **Fórmula:** Timestamp (Tempo entre o último backup) - Timestamp(ocorrência da falha)
    - **Coleta:** Configurar logs de transações, backups e sincronizações automáticas de dados.
    - **Pontuação de Julgamento:**

| **Bom** | **Regular** | **Insatisfatório** |
|:--------:|:-------------:|:-------------------:|
| $\leq 5$ minutos | 6 a 15 minutos | $> 15$ minutos |

**Justificativa:**
O RPO é uma métrica para avaliar a eficiência dos mecanismos de backup e replicação de dados. Mede a capacidade do sistema de minimizar perdas de informação em caso de falhas inesperadas, assegurando continuidade do aprendizado e confiança do usuário.

**Propósito** Garantir que os dados do usuário — como progresso, respostas e histórico de estudo — sejam recuperáveis em tempo aceitável.

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
4. [The Rule of Nines](https://www.penguinsolutions.com/en-us/resources/blog/rule-nines-availability-always-on-world)
5. [Fault Isolation in Systems](https://support.ptc.com/help/wrr/r13.0.0.0/en/wrr/ReferenceGuide/fmea/isolation_percentage.html)
6. [Establishing RPO and RTO Targets for Cloud Applications](https://aws.amazon.com/blogs/mt/establishing-rpo-and-rto-targets-for-cloud-applications/)
