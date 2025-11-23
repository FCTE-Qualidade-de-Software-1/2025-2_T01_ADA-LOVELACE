# Relatório de Resultado de Teste

---

# **Métrica 3.2: Recovery Point Objective (RPO)**

| Categoria | Detalhe |
| :--- | :--- |
| **Período de Coleta** | 23/11/2025 |
| **Responsável** | William Bernardo |
| **Foco da Análise** | Determinar o quanto de progresso o usuário perde após um incidente (queda de conexão) durante uma videoaula. |

---

## **Evidência dos Testes**

Cada teste consistiu em:

1. Iniciar a reprodução de uma videoaula;
2. Desligar a conexão manualmente;
3. Reabrir a videoaula após reconectar.

O procedimento foi repetido **5 vezes**.

**Exemplo de evidência em vídeo:**  
[Vídeo do teste](https://drive.google.com/file/d/1twZlQcJa5qgnzDjaDCwrbMNWf1XpHgGE/view?usp=sharing)

---

## **Análise dos Dados Coletados**

Durante os 5 testes consecutivos:

- A conexão foi interrompida manualmente em momentos diferentes.
- A plataforma sempre retomou muito próxima do ponto onde estava.
- Não houve perda de progresso em nenhuma das execuções.

---

## **Valores Medidos (5 Execuções)**

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

## **Classificação e Conclusão**

### **Resultado Final: Bom (Melhor Caso)**

Com **RPO médio = 0 min**, a plataforma apresentou **nenhuma perda de progresso** durante as 5 simulações.

| RPO | Avaliação |
|-----|-----------|
| ≤ 5 min | **Bom** |

### **Validação da Hipótese (H3.2)**  
A hipótese de que a plataforma **minimiza a perda de dados** em caso de falha foi **Confirmada**.

---

## **Evidências Resumidas das 5 Execuções**

| Etapa | Observação |
|-------|------------|
| Momento da falha | Conexão desligada durante a videoaula |
| Momento do retorno | Retorno sempre no exato ponto anterior à queda |
| Perda de progresso | **Nenhuma** em todas as 5 execuções |

---

# **Métrica 4.1: Recovery Time Objective (RTO)**

| Categoria | Detalhe |
| :--- | :--- |
| **Período de Coleta** | 24/11/2025 a 28/11/2025 |
| **Responsável** | William Bernardo |
| **Foco da Análise** | Tempo necessário para a plataforma restaurar o funcionamento após uma falha simulada. |

---

## **Análise dos Dados Coletados**

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

## **Evidência dos Testes**

O procedimento foi repetido **5 vezes**.

**Exemplo de evidência em vídeo:**  
[Vídeo do teste](https://drive.google.com/file/d/1GFQujzdcNFyG38wuwx3cWwqxG1Jpttr1/view?usp=sharing)


## **Valores Medidos (5 Execuções)**

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

## **Classificação e Conclusão**

### **Resultado Final: Bom (Melhor Cenário Possível)**

A plataforma atingiu o valor médio de **24.6 segundos** nas medições, demonstrando recuperação quase imediata.

| RTO | Avaliação |
|-----|-----------|
| ≤ 5 min | **Bom** |

### **Validação da Hipótese (H4.1)**  
A hipótese — de que a plataforma retorna rapidamente ao funcionamento após falhas — foi **Confirmada**.

---

## **Evidência dos Testes**

| Item | Observação |
|------|------------|
| Ação | Desconexão durante a resolução |
| Resultado | Retorno imediato, sem perda |
| RTO médio | 0 minutos |
| Ferramentas | Cronômetro, DevTools |
| Dispositivo | Galaxy A55 5G — Android 15 |

---

# **Resumo Final das Métricas**

| Métrica | Média dos 5 Testes | Resultado |
|---------|----------------------|-----------|
| **3.2 — RPO** | 0 min | **Bom (melhor caso)** |
| **4.1 — RTO** | 0 min | **Bom (melhor caso)** |

---
