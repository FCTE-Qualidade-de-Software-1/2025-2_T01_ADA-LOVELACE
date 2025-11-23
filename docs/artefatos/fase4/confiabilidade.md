# Relatório de Resultado de Teste

---

## **Métrica 3.2: Recovery Point Objective (RPO)**

| Categoria | Detalhe |
| :--- | :--- |
| **Data da Coleta** | 23/11/2025 |
| **Responsável** | William Bernardo |
| **Foco da Análise** | Determinar o quanto de progresso o usuário perde após um incidente (queda de conexão) durante uma videoaula. |

---

### **Evidência do Teste**

**Link para o Vídeo do Teste:**

[Vídeo do teste](https://drive.google.com/file/d/1Ezi3OLZg5oRyGbdowCsuUmWk6Tk1c_SH/view?usp=sharing)

## **Análise dos Dados Coletados**

O teste simulou uma **perda súbita de conexão** enquanto uma videoaula estava sendo reproduzida.  
O objetivo era verificar qual foi o **último ponto de salvamento consistente** antes da falha e, assim, medir o RPO real da plataforma.

Durante o teste:

- O vídeo estava em reprodução contínua.  
- A conexão foi interrompida manualmente para simular uma falha real.  
- Após restabelecer a conexão, o vídeo foi reaberto.  

**Resultado observado:**  
A plataforma retomou **exatamente no mesmo instante** em que a conexão foi perdida — sem qualquer perda de progresso.

### **Cálculo da Métrica (RPO)**

O RPO é calculado da seguinte forma:

```
RPO = Timestamp do último salvamento − Timestamp da falha
```

**Valores medidos:**

- **Timestamp do último salvamento:** mesmo instante da falha  
- **Timestamp da falha:** momento em que a conexão foi desligada  
- **Diferença (RPO):** 0 minutos

Portanto:

```
RPO = 0 min
```

---

## **Classificação e Conclusão**

### **Resultado do Teste: Bom (Melhor Caso)**

Com um RPO de **0 minutos**, a plataforma garantiu que **nenhuma perda de progresso** ocorreu durante a falha.

Segundo a classificação da métrica:

| RPO | Avaliação |
|-----|-----------|
| ≤ 5 min | **Bom** |

A plataforma atingiu o **melhor resultado possível** dentro da métrica.

### **Validação da Hipótese (H3.2)**

A hipótese H3.2 afirmava que a plataforma deveria **minimizar a perda de dados** em caso de falha, recuperando o estado do usuário com o mínimo de perda possível.  

Com RPO = 0 min, a hipótese é **Confirmada**.

A plataforma demonstrou possuir um mecanismo de salvamento eficiente e instantâneo, capaz de garantir a continuidade do estudo mesmo diante de interrupções inesperadas de conexão.

> **Observação:** Este resultado evidencia que o sistema grava continuamente o estado da videoaula, garantindo segurança e integridade do progresso do usuário.

---

## **Evidências do Teste**

| Etapa | Observação |
|-------|------------|
| Momento da falha | Conexão foi desligada enquanto o vídeo estava em execução. |
| Momento do retorno | Plataforma abriu o vídeo exatamente no instante anterior à queda. |
| Perda de progresso | **Nenhuma** (0 minutos). |

**Link para o Vídeo do Teste:**

[Vídeo do teste](https://drive.google.com/file/d/1EtDV-ZDyGJk3p3L3KN7r6oSc3niFVGTH/view?usp=sharing)

---

## **Resumo Final do Comportamento da Plataforma**

- O salvamento do progresso da videoaula ocorre **em tempo real**.  
- O retorno após incidente é **preciso** e **imediato**, sem atrasos.  
- O sistema atende plenamente o esperado pelo RPO.  

---

## **Métrica 4.1: Recovery Time Objective (RTO)**

| Categoria | Detalhe |
| :--- | :--- |
| **Período de Coleta** | 24/11/2025 a 28/11/2025 |
| **Responsável** | William Bernardo |
| **Foco da Análise** | Tempo necessário para a plataforma Khan Academy restaurar o funcionamento após uma falha simulada |

---

## **Análise dos Dados Coletados**

O teste consistiu em iniciar um exercício na plataforma, responder algumas questões e, então, **forçar uma desconexão da internet**. O objetivo era medir quanto tempo a plataforma demoraria para retornar ao estado funcional normal após:

1. A queda da conexão (falha).  
2. A reconexão posterior (recuperação).  

O fluxo observado foi o seguinte:

- Durante o exercício, a conexão foi interrompida.  
- O usuário retornou à **home**, ainda sem internet.  
- Após reconectar a internet, o avaliador retornou ao exercício.  
- **Resultado:** O exercício foi restaurado imediatamente **no exato ponto em que havia sido deixado**, com todas as respostas e progresso preservados — **sem perda de checkpoint** e sem qualquer tempo perceptível de restauração.

### **Valores observados:**

- **Timestamp da falha:** T₁  
- **Timestamp da recuperação:** T₁ (restauração instantânea após reconexão)  
- **Diferença calculada (RTO):** 0 minutos

---

## **Cálculo da Métrica (RTO)**

A métrica RTO é definida como:

```
RTO = Timestamp da recuperação – Timestamp da falha
```

Aplicando os valores observados:

```
RTO = 0 minutos
```

---

## **Classificação e Conclusão**

### **Resultado do Teste: Bom (Melhor Cenário Possível)**

O valor de RTO observado foi de **0 minutos**, indicando restauração imediata da funcionalidade assim que a conexão foi retomada.

De acordo com a classificação estabelecida:

- **≤ 5 minutos → Bom**  
- **0 minutos → Melhor caso possível dentro do nível “Bom”**

### **Validação da Hipótese (H4.1)**

A hipótese **H4.1**, que pressupõe que a plataforma retorna rapidamente ao funcionamento após falhas, é **Confirmada**.

A plataforma demonstrou excelente resiliência ao:

- Restaurar o exercício sem perda de dados.  
- Recolocar o usuário exatamente no fluxo anterior.  
- Requerer **zero tempo de espera** para voltar ao funcionamento pleno.  

> **Observação:** A restauração imediata sugere que a plataforma mantém estados críticos localmente ou em memória, garantindo fluidez mesmo em cenários de interrupção temporária.

---

## **Evidência do Teste**

| Item | Evidência |
|------|----------|
| **Ação Realizada** | Desconexão durante resolução de exercício |
| **Resultado** | Retorno imediato ao exercício, sem perda de progresso |
| **RTO Registrado** | 0 minutos |
| **Ferramentas utilizadas** | Cronômetro + Chrome DevTools |
| **Dispositivo** | Smartphone Galaxy A55 5G — Android 15 |

---

## **Resumo Final**

O teste demonstrou que a plataforma Khan Academy possui um comportamento altamente eficiente de recuperação, garantindo ao usuário continuidade plena do fluxo de estudo após uma falha. A Métrica 4.1 (RTO) foi atendida com excelência.

