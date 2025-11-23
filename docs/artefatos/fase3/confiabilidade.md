#  Procedimentos de Coleta - Confiabilidade

## Métrica 3.2: Recovery Point Objective (RPO)

**Data de coleta:** 23/11/2025  
**Método:** Manual + análise de logs  
**Dispositivos:** O membro responsável *William Bernardo* analisará a aplicação em um computador e um celular para comparar os timestamps registrados no sistema.

---

### Descrição Geral da Coleta

A coleta será realizada por meio da análise de logs de backup, logs de sincronização de dados e registros de transações, buscando identificar:

1. O **último ponto de salvamento consistente** antes de um incidente (último backup ou sync completo).  
2. O **timestamp da falha** (queda, indisponibilidade, erro crítico).

### **Cálculo do RPO**

RPO = Timestamp do último salvamento – Timestamp da falha

*Todos os valores serão registrados em uma planilha.*

---

### Ferramentas Utilizadas

#### **Console de Logs do Navegador**
Usado para visualizar mensagens, erros e timestamps relacionados a:
- operações de gravação local  
- sincronizações automáticas  
- erros críticos  

#### **Developer Tools – Network**
Permite verificar:
- envio de dados ao backend  
- requisições de sync  
- respostas indicando sucesso ou falha  
- carga de dados  

#### **Planilha Google Sheets**
Utilizada para:
- Registrar timestamps do último backup válido  
- Registrar o timestamp da falha  
- Registrar diferenças (em minutos)  
- Classificar automaticamente conforme a regra:

| Classificação      | RPO |
|--------------------|------|
| **Bom**            | ≤ 5 min |
| **Regular**        | 6 a 15 min |
| **Insatisfatório** | > 15 min |

---

### Dispositivos Utilizados Nos Testes

Os dispositivos simulam o ambiente real de estudo da plataforma Khan Academy.

### **Notebook Notebook Dell**
- **SO:** Ubuntu 24.04.3 LTS
- **CPU:** Intel Core i7-1165G7 @ 2.80GHz
- **RAM:** 16 GB DDR5  
- **Navegador:** Chrome 142+  

---

### Como Realizar a Coleta

1. Abrir o **Khan Academy** no Chrome.  
2. Iniciar ações que ativem salvamentos automáticos (ex.: exercícios, progresso, configurações).  
3. Abrir os *Developer Tools* e monitorar logs e eventos de **sync**.  
4. Forçar ou identificar falhas naturais (timeout, erro 500, desconexão).  
5. Registrar o **timestamp do último salvamento completo antes da falha**.  
6. Registrar o **timestamp exato da falha**.  
7. Calcular a diferença entre os dois valores (em minutos).  
8. Registrar na planilha:
   - Timestamp do backup válido  
   - Timestamp da falha  
   - RPO calculado  
   - Observações  
   - Dispositivo utilizado  
   - Data e horário  

---

### Análise dos Dados

A planilha calculará automaticamente o RPO de cada incidente.  
A classificação usada será:

| RPO (minutos) | Avaliação |
|---------------|-----------|
| ≤ 5           | Bom |
| 6 a 15        | Regular |
| > 15          | Insatisfatório |

---

##  Métrica 4.1: Recovery Time Objective (RTO)

**Período de coleta:** 24/11/2025 a 28/11/2025  
**Método:** Manual  
**Dispositivos:** O avaliador *William Bernardo* utilizará um notebook e um celular para observar o tempo de retorno da funcionalidade após incidentes.

---

### Descrição Geral da Coleta

A coleta será feita a partir da observação do tempo necessário para restaurar a funcionalidade total da aplicação após uma falha simulada ou detectada.

O avaliador irá:

1. Identificar um incidente (queda, crash, erro crítico, travamento).  
2. Marcar o **timestamp da falha**.  
3. Monitorar até que a plataforma volte a funcionar completamente.  
4. Marcar o **timestamp da recuperação**.

### **Cálculo do RTO**

RTO = Timestamp da recuperação – Timestamp da falha

*Todos os resultados serão registrados em planilha.*

---

## Ferramentas Utilizadas

### **Cronômetro / Timer**
Usado para medir com precisão o tempo entre a falha e a recuperação.

### **Navegador Google Chrome**
- Usado para realizar todas as operações da coleta.  
- **Versão exigida:** Chrome 142+

### **Planilha Google Sheets**
Utilizada para:
- Registrar o timestamp da falha  
- Registrar o timestamp da recuperação  
- Calcular o RTO automaticamente  
- Classificar conforme a regra:

| Classificação   | RTO |
|-----------------|-----|
| **Bom**         | ≤ 5 min |
| **Regular**     | 6 a 60 min |
| **Insatisfatório** | > 60 min |

---

### Dispositivos Utilizados Nos Testes

Os dispositivos simulam o ambiente real de estudo da plataforma Khan Academy.

### **Notebook Notebook Dell**
- **SO:** Ubuntu 24.04.3 LTS
- **CPU:** Intel Core i7-1165G7 @ 2.80GHz
- **RAM:** 16 GB DDR5  
- **Navegador:** Chrome 142+  

---

### Como Realizar a Coleta

1. Abrir o **Khan Academy** no navegador.  
2. Identificar uma situação de falha real ou simular (ex.: desconexão de rede, interrupção no carregamento).  
3. Marcar o **timestamp exato da falha**.  
4. Aguardar até que a aplicação volte a funcionar sem erros.  
5. Marcar o **timestamp de restauração total** da funcionalidade.  
6. Calcular o tempo entre falha e restauração (em minutos).  
7. Registrar na planilha:
   - Timestamp da falha  
   - Timestamp da recuperação  
   - RTO calculado  
   - Observações  
   - Dispositivo utilizado  
   - Data e hora  

---

### Análise dos Dados

A planilha classificará automaticamente o RTO observado.  
A tabela usada será:

| RTO (minutos) | Avaliação |
|---------------|-----------|
| ≤ 5           | Bom |
| 6 a 60        | Regular |
| > 60          | Insatisfatório |
