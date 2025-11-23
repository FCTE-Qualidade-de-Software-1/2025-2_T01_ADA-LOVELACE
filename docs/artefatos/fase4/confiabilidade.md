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

---

## **Resumo Final do Comportamento da Plataforma**

- O salvamento do progresso da videoaula ocorre **em tempo real**.  
- O retorno após incidente é **preciso** e **imediato**, sem atrasos.  
- O sistema atende plenamente o esperado pelo RPO.  

---

