## Relatório de Resultado de Teste

---

## Maturidade

### **Métrica 1.1: Crash Rate (CR)**

| Categoria | Detalhe |
| :--- | :--- |
| **Período de Coleta** | 24/11/2025 |
| **Responsável** | Mateus Vieira |
| **Foco da Análise** | Determinar quantas vezes do total de testes houve crash na aplicação, entende-se crash como aplicação inutilizável com necessidade de reinício. |

---

### **Evidência dos Testes**

Cada teste consistiu em:

1. Acessar a página inicial de estudante no Khan Academy
2. Selecionar uma disciplina/curso
      1. Entrar na unidade 1
      2. Dar play em ao menos 1 vídeo durante o curso
      3. Entrar e interagir com 5 páginas do curso, sejam de leitura, execício ou testes
3. Voltar para a página inicial do estudante clicando na logo do Khan Academy

O procedimento foi repetido **10 vezes**.

**Evidência da 1ª execução em Vídeo:**

<iframe src="https://drive.google.com/file/d/1xVfoMgUgs-dXUVajc4S01kfJQbSovcyS/preview" width="1080" height="480"></iframe>

Vídeo: [Link 1.1](https://drive.google.com/file/d/1xVfoMgUgs-dXUVajc4S01kfJQbSovcyS/view?usp=sharing)

---

### **Análise dos Dados Coletados**

Durante os 10 testes consecutivos:

- Não houve nenhum crash nas sessões, todas as ações foram executadas sem problema.
- Em 2 sessões o tempo de retorno para a tela inicial foi maior que o esperado, mas não houve crash e essa análise está fora de tal métrica. Logo, vem apenas como observação,

---

### **Cálculo dos Crashes**

$CR = \frac{Número\ de\ Crashes}{Número\ Total\ de\ Sessões} \times 100\%$

$CR = \frac{0}{10} \times 100\%$

$CR = 0\%$

---

### **Classificação e Conclusão**

#### **Resultado Final: Bom (Melhor Caso)**

Com **CR = 0%**, a plataforma apresentou **mínimo número de crashes** durante as 10 simulações.

| CR            | Avaliação |
|---------------|-----------|
| $\leq 0.15\%$ | **Bom**   |

**Observação:** Para ter certeza sobre a porcentagem de crashes por sessão e possível quebra da hipótese (H1.1) criada na fase 2, seriam necessárias pelo menos 10.000 reproduções. Entretanto, o time não apresentou tempo hábil para realiza-las, logo foram feitos apenas 10 testes.

#### **Validação da Hipótese (H1.1)**

A hipótese de que aplicações com boa avaliação nos meios de instalação e comentários como Google Play, App Store e Google devem apresentar CR menos ou igual a 0.15% é verdadeira. Contudo, deve-se entender a limitação do nosso teste devido ao baixo volume de reprodução, como já anteriormente.

### **Métrica 1.2: Mean Time Between Failure (MTBF)**

---

## Disponibilidade

### **Métrica 2.1: Average Response Time (ART)**

| Categoria | Detalhe |
| :--- | :--- |
| **Período de Coleta** | 23/11/2025 - 24/11/2025 (22h às 09h) |
| **Responsável** | Mateus Vieira |
| **Foco da Análise** | Determinar qual o tempo de resposta médio para a ação de buscar cursos dentro da plataforma por meio do campo de `search`. |

---

### **Evidência dos Testes**

Cada teste consistiu em:

1. O script selecionar qual seria o termo buscado no momento: *algebra, biologia, python, historia ou economia*
2. Executar uma requisição GET na URL: `https://www.khanacademy.org/search?referer=%2Fprofile%2Fme%2Fcourses&page_search_query=${search}`
3. Registrar as informações úteis, já ditas da Fase 3, sobre a requisição

O procedimento foi repetido **1000 vezes**.

**Evidência das execuções em Vídeo:**

<iframe src="https://drive.google.com/file/d/1Tm-J96FRxOSkyUeS5QqCnkoo_gq-OubW/preview" width="1080" height="480"></iframe>

Vídeo: [Link 2.1](https://drive.google.com/file/d/1HXsEP0AqCs0P1eEJs1bi_XQktK-bmA_a/view?usp=sharing)

---

### **Análise dos Dados Coletados**

Durante os 1000 testes consecutivos:

- Não houve nenhum erro nas requisições, todas retornaram `200 OK`.
- O maior tempo de resposta foi de 693ms, ou seja, não ultrapassou o limite de 1s.

---

### **Valores Medidos (1000 Execuções)**

<iframe src="https://docs.google.com/spreadsheets/d/e/2PACX-1vTsBl-oW3dtp-6EJno83GiPCerwn0i54lb0I78XsXIovtXQcdwTf1v9YpM9Rj32Ci_fL7Jm_7xUsJ2j/pubhtml?gid=1173283656&amp;single=true&amp;widget=true&amp;headers=false" width="100%" height="400"></iframe>

### **Cálculo da Média**

$ART\_médio = \frac{\sum\ elapsed\_ms}{1000}$

$ART\_médio = 341.085ms$

---

### **Classificação e Conclusão**

#### **Resultado Final: Bom (Melhor Caso)**

Com **ART médio = 341ms**, a plataforma apresentou **baixo tempo de resposta** durante as 1000 simulações.

| ART | Avaliação |
|-----|-----------|
| ≤ 1 s | **Bom** |

#### **Validação da Hipótese (H2.1)**  

A hipótese de que para ações críticas, como a busca por cursos que foi utilizada, teria uma média menor que 1s, foi confirmada.

- Ações Críticas: Aquelas que impedem o usuário de continuar utilizando a plataforma.
    - Como alguém continua usando a aplicação se não consegue ou demora muito para simplesmente encontrar o curso?
        - Não continua, se frustra.
    - Logo, buscar por cursos torna-se uma ação crítica.

### **Métrica 2.2: Availability Percentage (AP)**

| Categoria | Detalhe |
| :--- | :--- |
| **Período de Coleta** | 24/11/2025 |
| **Responsável** | Mateus Vieira |
| **Foco da Análise** | Determinar qual a porcentagem de disponibilidade da plataforma do Khan Academy nos últimos 60 dias. |

---

### **Evidência da Coleta**

A coleta consistiu em:

1. Abrir o StatusGator e verificar para os últimos 60 dias quando houve queda na plataforma do Khan Academy e por quanto tempo durou
2. Abrir o Khan Academy Status Page, página official, e validar para cada indício no StatusGator se a queda realmente ocorreu
3. Somar o tempo total de queda dos últimos 60 dias para a plataforma
4. Realizar o calculo final de disponibilidade

**Evidência da Coleta em Vídeo:**

<iframe src="https://drive.google.com/file/d/1HXsEP0AqCs0P1eEJs1bi_XQktK-bmA_a/preview" width="1080" height="480"></iframe>

Vídeo: [Link 2.2](https://drive.google.com/file/d/1Tm-J96FRxOSkyUeS5QqCnkoo_gq-OubW/view?usp=sharing)

---

### **Análise dos Dados Coletados**

Durante a coleta:

- Foi percebido 3 dias de queda na plataforma do Khan Academy, sendo esses:
    - 2 de Outubro de 2025 (35min)
    - 30 de Outubro de 2025 (2hrs e 29min)
    - 19 de Novembro de 2025 (10min)
- Houve um outro dia, 31 de Outubro de 2025, com um período enorme de problemas técnicos em um total de 17hrs e 35min, entretanto não foi relatado como queda do sistema. Logo, entendendo que esse dia se tratou apenas de problemas localizados dentro da plataforma o mesmo não entrará no calculo de indisponibilidade

---

### **Cálculo da Porcentagem**

$Tempo\ Disponível = (60 \times 24 \times 60) - (35 + 149 + 10) = 86206$

$AP = \frac{86206}{86400} \times 100 = 99.775$

$AP = 99.775\%$

---

### **Classificação e Conclusão**

#### **Resultado Final: Bom (Melhor Caso)**

Com **AP = 99.775%**, a plataforma apresentou **alto tempo de disponibilidade**.

| AP (porcentagem) | Avaliação      |
| ---------------- | -------------- |
| $\ge 99\%$       | Bom            |

#### **Validação da Hipótese (H2.2)**  

A hipótese de que a aplicação teria disponibilidade maior que 99% e, portanto, não ficaria mais de 87.6 horas fora do ar durante o ano está correta. Foi analisado o período de 60 dias, mas tendo em vista um padrão e replicando o resultado para 1 ano, teríamos um indisponibilidade anual de no máximo 19.71 horas

---

## Tolerância a Falhas

### **Métrica 3.2: Recovery Point Objective (RPO)**

| Categoria | Detalhe |
| :--- | :--- |
| **Período de Coleta** | 23/11/2025 |
| **Responsável** | William Bernardo |
| **Foco da Análise** | Determinar o quanto de progresso o usuário perde após um incidente (queda de conexão) durante uma videoaula. |

---

### **Evidência dos Testes**

Cada teste consistiu em:

1. Iniciar a reprodução de uma videoaula;
2. Desligar a conexão manualmente;
3. Reabrir a videoaula após reconectar.

O procedimento foi repetido **5 vezes**.

**Exemplo de evidência em vídeo:**  
[Vídeo do teste](https://drive.google.com/file/d/1twZlQcJa5qgnzDjaDCwrbMNWf1XpHgGE/view?usp=sharing)

---

### **Análise dos Dados Coletados**

Durante os 5 testes consecutivos:

- A conexão foi interrompida manualmente em momentos diferentes.
- A plataforma sempre retomou muito próxima do ponto onde estava.
- Não houve perda de progresso em nenhuma das execuções.

---

### **Valores Medidos (5 Execuções)**

Para cada teste:

RPO = Timestamp do último salvamento − Timestamp da falha

| Execução | RPO observado |
|---------|--------------|
| Teste 1 | 0 s |
| Teste 2 | 15 s |
| Teste 3 | 30 s |
| Teste 4 | 26 s |
| Teste 5 | 28 s |

### **Cálculo da Média**

RPO_médio = (0 + 15 + 30 + 26 + 28) / 5

RPO_médio = 20 segundos

---

### **Classificação e Conclusão**

#### **Resultado Final: Bom (Melhor Caso)**

Com **RPO médio = 0 min**, a plataforma apresentou **nenhuma perda de progresso** durante as 5 simulações.

| RPO | Avaliação |
|-----|-----------|
| ≤ 5 min | **Bom** |

#### **Validação da Hipótese (H3.2)**  

A hipótese de que a plataforma **minimiza a perda de dados** em caso de falha foi **Confirmada**.

---

### **Evidências Resumidas das 5 Execuções**

| Etapa | Observação |
|-------|------------|
| Momento da falha | Conexão desligada durante a videoaula |
| Momento do retorno | Retorno sempre no exato ponto anterior à queda |
| Perda de progresso | **Nenhuma** em todas as 5 execuções |

---

### **Métrica 4.1: Recovery Time Objective (RTO)**

| Categoria | Detalhe |
| :--- | :--- |
| **Período de Coleta** | 24/11/2025 a 28/11/2025 |
| **Responsável** | William Bernardo |
| **Foco da Análise** | Tempo necessário para a plataforma restaurar o funcionamento após uma falha simulada. |

---

### **Análise dos Dados Coletados**

Cada um dos 5 testes seguiu o fluxo:

1. Início de um exercício;  
2. Falha simulada (desligamento da conexão);  
3. Retorno à home sem internet;  
4. Reconexão;  
5. Reabertura do exercício para verificar retomada.

Em todas as execuções, o exercício foi restaurado:

- **Imediatamente**, no exato ponto anterior à falha;
- **Sem perda de progresso**;
- **Sem tempo de espera perceptível**.

---

### **Evidência dos Testes**

O procedimento foi repetido **5 vezes**.

**Exemplo de evidência em vídeo:**  
[Vídeo do teste](https://drive.google.com/file/d/1GFQujzdcNFyG38wuwx3cWwqxG1Jpttr1/view?usp=sharing)

### **Valores Medidos (5 Execuções)**

RTO = Timestamp da recuperação – Timestamp da falha

| Execução | RTO observado |
|---------|---------------|
| Teste 1 | 10 s |
| Teste 2 | 28 s |
| Teste 3 | 33 s |
| Teste 4 | 25 s |
| Teste 5 | 27 s |

### **Cálculo da Média**

RTO_médio = (10 + 28 + 33 + 25 + 27) / 5
RTO_médio = 24.6 segundos

---

### **Classificação e Conclusão**

#### **Resultado Final: Bom (Melhor Cenário Possível)**

A plataforma atingiu o valor médio de **24.6 segundos** nas medições, demonstrando recuperação quase imediata.

| RTO | Avaliação |
|-----|-----------|
| ≤ 5 min | **Bom** |

#### **Validação da Hipótese (H4.1)**  

A hipótese — de que a plataforma retorna rapidamente ao funcionamento após falhas — foi **Confirmada**.

---

### **Evidência dos Testes**

| Item | Observação |
|------|------------|
| Ação | Desconexão durante a resolução |
| Resultado | Retorno imediato, sem perda |
| RTO médio | 0 minutos |
| Ferramentas | Cronômetro, DevTools |
| Dispositivo | Galaxy A55 5G — Android 15 |

---

## **Resumo Final das Métricas**

| Métrica | Média dos 5 Testes | Resultado |
|---------|----------------------|-----------|
| **3.2 — RPO** | 0 min | **Bom (melhor caso)** |
| **4.1 — RTO** | 0 min | **Bom (melhor caso)** |

---
