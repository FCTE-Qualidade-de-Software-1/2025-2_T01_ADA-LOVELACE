# Confiabilidade

## Maturidade

### Métrica 1.1: Crash Rate (CR)

### Métrica 1.2: Mean Time Between Failure (MTBF)

### Procedimento de Coleta

**Período de coleta:** 21/11/2025 a 24/11/2025
**Método:** Manual - O membro responsável **Renan Vieira** testará a aplicação.

**Computador:**

* **Modelo:** Notebook Nitro V
* **Sistema Operacional:** Windows

**Registro de falhas:**
Sempre que ocorrer uma falha (qualquer interrupção ou comportamento inesperado que impeça o uso normal), registrar o evento.
Anotar as informações mínimas: data, hora, ação realizada e dispositivo utilizado.
Registrar o tempo total de operação do sistema desde o início da sessão até a ocorrência da falha.

**Ferramenta de armazenamento:** Todos os registros serão centralizados em uma planilha no Google Sheets, com colunas separadas por membro da equipe, tempo de operação e falhas encontradas.

**Cálculo do MTBF:**
Ao final da semana, calcular a média entre todos os membros.

### Pontuação de Julgamento

| MTBF (horas) | Avaliação |
| :--- | :--- |
| ≥ 30 | Bom |
| 30 a 29 | Regular |
| < 30 | Insatisfatório |

## Disponibilidade

### Métrica 2.1: Average Response Time (ART)

**Data de coleta:** 23/11/2025 – 24/11/2025 (22h às 09h)  
**Método:** Automatizado  
**Dispositivo:** O membro responsável *Mateus Vieira* vai utilizar um computador dedicado para rodar o script de testes 

---

### Descrição Geral da Coleta

A coleta será realizada por meio de um **script automatizado em Node.js**, responsável por enviar requisições periódicas para as funcionalidades críticas do sistema. Cada requisição terá seu **tempo de resposta capturado automaticamente**.

A funcionalidade monitorada será:

1. Pesquisa por disciplina

Os resultados serão registrados continuamente até que o total acumulado seja de **1000 requisições**.

---

### Ferramentas Utilizadas

#### **Script Node.js**

Responsável por:

* Disparar requisições a cada intervalo configurado (40s)
* Medir tempos de resposta
* Registrar os resultados no CSV

#### **Arquivo CSV (armazenamento local)**

Utilizado para:

* Guardar o conjunto completo de requisições
* Facilitar posterior análise estatística
* Calcular métricas agregadas

---

### Dispositivo Utilizado Nos Testes

* **RAM:** 24 GB
* **CPU:** Intel Core i3-9100F
* **SO:** Debian 12

**Periodicidade das requisições:** 90 requisições por hora  
**Volume total esperado:** 1000 requisições

---

### Como Realizar a Coleta

1. Escrever o script automatizado de requisições
2. Iniciar o script de requisições para rodar até alcançar 1000 ações
3. Durante suas 12h seguidas, o script armazenará automaticamente:
      1. Timestamp do envio
      2. Timestamp da resposta
      3. Tempo total de resposta (ms)
      4. Endpoint acionado
      5. Status da resposta HTTP

Os dados serão gravados em um **arquivo CSV**, contendo uma linha por requisição.

---

### Cálculo do ART

Após a coleta, será calculada a métrica **Average Response Time (ART)** da seguinte forma:

$ART = \frac{\sum\ de\ Tempos\ de\ Resposta}{Número\ Total\ de\ Requisições}$

---

### Análise dos Dados

A classificação usada para a média das requisições do sistema será:

| ART (segundos) | Avaliação      |
| -------------- | -------------- |
| **≤ 1**        | Bom            |
| **1.1 a 3**    | Regular        |
| **> 3**        | Insatisfatório |

### Métrica 2.2: Availability Percentage (AP)

**Data de coleta:** 24/11/2025  
**Método:** Leitura Manual (Coleta Automática)  
**Dispositivo:** O membro responsável *Mateus Vieira* utilizará as plataformas StatusGator e Khan Academy Status Page, serviços especializados em monitoramento de disponibilidade, incidentes, interrupções e históricos de uptime. A avaliação será feita com base nos períodos registrados nessas plataformas, verificando se houve downtime, instabilidade ou degradação de serviços da Khan Academy durante o período analisado.

---

### Descrição Geral da Coleta

A coleta de disponibilidade não será feita por meio de testes de carga ou requisições diretas ao sistema, mas sim por meio do monitoramento oficial e terceirizado das plataformas StatusGator e do dashboard de status da Khan Academy.

Ambas fornecem:

* Histórico de uptime por dia/mês
* Registros de indisponibilidades
* Períodos de manutenção
* Logs de incidentes e degradação de desempenho
* Classificação por severidade e impacto

A análise verificará:

1. Se houve algum período com interrupção parcial ou total no serviço
2. A duração total dos incidentes
3. A porcentagem de disponibilidade calculada pelas próprias plataformas

---

### Ferramentas Utilizadas

**StatusGator**

* Plataforma que integra relatórios de status de múltiplos serviços.
* Permite visualizar uptime, incidentes e manutenção programada.
* Exibe gráficos, histórico completo e logs de falhas.

**Khan Academy Status Page**

* Página oficial que reporta disponibilidade dos serviços da Khan Academy.
* Mostra interrupções em tempo real e incidentes passados.
* Inclui:
    * Uptime mensal
    * Erros, latência, performance
    * Serviços afetados (site, APIs, vídeos, login, dashboards)

---

### Dispositivo Utilizado para Consulta

* **RAM:** 16 GB
* **CPU:** Ryzen 5 5600G
* **SO:** Ubuntu 22.04 LTS

**Observação:** A coleta é manual (via leitura das plataformas), portanto o dispositivo não influencia o resultado da métrica, servindo apenas como registro documental.

---

### Como Realizar a Coleta

1. Acessar o StatusGator filtrando pelo serviço Khan Academy
2. Acessar o Khan Academy Status Page
3. Registrar (Para os Últimos 60 Dias):
      * Períodos de indisponibilidade reportados
      * Duração dos incidentes
      * Impacto no serviço
      * Uptime mensal apresentado pela plataforma
4. Consolidar os dados dos dois serviços, utilizando o StatusGator como fonte agregadora e o status oficial como validação
5. Calcular a porcentagem de disponibilidade

---

### Cálculo do AP

Após a coleta, será calculada a métrica **Availability Percentage (AP)** da seguinte forma:

$AP = \frac{Total\ Available\ Time\ (min)}{60 \times 24 \times 60} \times 100$

---

### Análise dos Dados

A classificação usada para a porcentagem relativa ao tempo de disponibilidade da plataforma será:

| AP (porcentagem) | Avaliação      |
| ---------------- | -------------- |
| $\ge 99\%$       | Bom            |
| $99\%$ a $98\%$  | Regular        |
| $\lt 98\%$       | Insatisfatório |

---

## Tolerância a Falhas

### Métrica 3.1: Fault Isolation Rate (FIR)

### Procedimento de Coleta
**Período de Coleta:** 21/11/2025 a 24/11/2025

**Método:** Manual com Suporte de Ferramentas de Desenvolvedor

**Dispositivos:**
O membro responsável **Renan Vieira** testará a aplicação:

* **Computador:** Notebook Nitro V (Windows)

**Ferramentas Adicionais:**

* Console do Navegador (DevTools - F12) para captura de logs
* Ferramenta de screenshot (Windows Snipping Tool)

### Registro de Falhas
**Definição de Falha:**
Uma falha ocorre quando há qualquer interrupção ou comportamento inesperado que impede o usuário de completar uma tarefa. Exemplos:

* Funcionalidade não responde (botão não clica, formulário não submete)
* Página não carrega após 30 segundos
* Erro visível na interface
* Perda de progresso em exercícios ou vídeos

**Definição de Isolamento Bem-Sucedido:**
Uma falha é considerada corretamente isolada quando:

* É possível identificar o componente específico que falhou (ex: player de vídeo, sistema de exercícios, menu de navegação)
* As outras funcionalidades principais continuam operacionais
* O usuário consegue contornar a falha usando um caminho alternativo

**Informações a Registrar:**
Para cada falha detectada, anotar:

| Campo | Descrição |
| :--- | :--- |
| **ID da Falha** | Número sequencial (F001, F002, ...) |
| **Data e Hora** | DD/MM/AAAA HH:MM |
| **Dispositivo** | Desktop (SO) / Mobile (Android/iOS) |
| **Componente Afetado** | Especificar: Player de vídeo / Exercícios / Navegação / Perfil / Progresso / Certificação / Outro |
| **Descrição da Falha** | Breve descrição do problema encontrado |
| **Ação que Gerou** | O que estava sendo feito quando a falha ocorreu |
| **Outros Componentes Testados** | Listar quais outras funcionalidades foram testadas após a falha |
| **Status dos Outros Componentes** | Funcionando normalmente / Também afetados |
| **Isolamento Bem-Sucedido?** | SIM ou NÃO |
| **Justificativa** | Explicar por que foi ou não isolada |
| **Logs de Erro** | Se houver erros no Console, copiar a mensagem principal |
| **Caminho Alternativo** | Descrever se existe forma de contornar o problema |

**Exemplo Prático de Registro:**
*Cenário 1 - Isolamento Bem-Sucedido:*

| Campo | Valor |
| :--- | :--- |
| **ID** | F001 |
| **Componente Afetado** | Player de vídeo |
| **Descrição** | Vídeo não carrega, tela fica preta |
| **Outros Componentes Testados** | Exercícios, Navegação, Perfil |
| **Status** | Todos funcionando normalmente |
| **Isolamento** | SIM ✓ |
| **Justificativa** | Apenas o player falhou, restante do sistema operacional |

*Cenário 2 - Isolamento Mal-Sucedido:*

| Campo | Valor |
| :--- | :--- |
| **ID** | F002 |
| **Componente Afetado** | Sistema de login |
| **Descrição** | Não consegue fazer login |
| **Outros Componentes Testados** | Todas as páginas requerem autenticação |
| **Status** | Nenhuma funcionalidade acessível |
| **Isolamento** | NÃO ✗ |
| **Justificativa** | Falha impede acesso a todo o sistema |

**Ferramenta de Armazenamento:**
Todos os registros serão centralizados em uma planilha no Google Sheets, com colunas separadas para:

* Informações da falha
* Análise de isolamento
* Membro responsável pelo registro
* Evidências (links para screenshots, se aplicável)

**Cálculo do FIR:**
Ao final da semana:

1. Contar o número total de falhas detectadas por todos os membros
2. Contar quantas falhas foram corretamente isoladas (marcadas como "SIM")
3. Aplicar a fórmula:
   FIR = (Número de Falhas Corretamente Isoladas) ÷ (Número Total de Falhas Detectadas) × 100%

### Pontuação de Julgamento
| FIR | Avaliação |
| :--- | :--- |
| ≥ 92% | Bom |
| 90% a 91% | Regular |
| < 90% | Insatisfatório |


### Métrica 3.2: Recovery Point Objective (RPO)

**Data de coleta:** 23/11/2025  
**Método:** Manual + análise de logs  
**Dispositivos:** O membro responsável *William Bernardo* analisará a aplicação em um computador e um celular para comparar os timestamps registrados no sistema.

---

### Descrição Geral da Coleta

A coleta será realizada por meio da análise de logs de backup, logs de sincronização de dados e registros de transações, buscando identificar:

1. O **último ponto de salvamento consistente** antes de um incidente (último backup ou sync completo).  
2. O **timestamp da falha** (queda, indisponibilidade, erro crítico).

#### **Cálculo do RPO**

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

#### **Notebook Notebook Dell**

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

## Recuperabilidade

### Métrica 4.1: Recovery Time Objective (RTO)

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

#### **Cálculo do RTO**

RTO = Timestamp da recuperação – Timestamp da falha

*Todos os resultados serão registrados em planilha.*

---

### Ferramentas Utilizadas

#### **Cronômetro / Timer**

Usado para medir com precisão o tempo entre a falha e a recuperação.

#### **Navegador Google Chrome**

- Usado para realizar todas as operações da coleta.  
- **Versão exigida:** Chrome 142+

#### **Planilha Google Sheets**

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

#### **Notebook Notebook Dell**

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
