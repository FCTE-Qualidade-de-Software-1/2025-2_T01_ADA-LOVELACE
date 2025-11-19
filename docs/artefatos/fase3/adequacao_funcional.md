## 📋 Especificações de Teste: Métrica 1.1 - Adequação Funcional

---

### 👥 Divisão de Responsabilidades e Gerenciamento

A divisão de métricas foi alocada aos membros do projeto que participaram das atividades de adequação funcional desde a Fase 1.

| Participante | Métrica |
| :--- | :--- |
| **Pedro Gois** | 3.1 |
| **Mateus Henrique** | 1.1 |
| **Mateus Cavalcante** | 2.1 |

> Um quadro Kanban foi organizado no Jira para que cada participante registre o andamento do planejamento de testes das suas respectivas métricas, garantindo melhor organização e rastreabilidade do projeto.

---

### 🛡️ Estratégia de Teste - Métrica 1.1

**Métrica:** Percentual de funcionalidades essenciais implementadas e funcionais.

#### 🗓️ Cronograma e Método de Coleta

* **Período de Coleta:** 24/11/2025 a 28/11/2025
* **Método:** Manual
* **Responsável:** Mateus Henrique

#### 📝 Procedimento de Coleta

O avaliador verificará as funcionalidades essenciais (RF01 a RF16, definidas na Fase 1) de forma individual. Para cada funcionalidade, será avaliado se:

1.  **Implementada:** A funcionalidade existe no sistema.
2.  **Operacional/Funcional:** A funcionalidade executa sua ação principal **sem falhas críticas**, travamentos ou comportamento inesperado.
3.  **Utilizável:** O recurso pode ser usado conforme o esperado.

Todos os resultados serão meticulosamente registrados na planilha de testes.

#### 💻 Ferramentas e Dispositivos Utilizados

| Tipo | Especificação | Detalhes |
| :--- | :--- | :--- |
| **Navegador** | Google Chrome 142+ | Todos os testes serão realizados exclusivamente nesta versão. |
| **Planilha** | Google Sheets | **Função:** Registro de RFs, marcação de status (Implementada/Funcional), Observações, Erros/Crashes e **cálculo automático da métrica**. |

---

### 📱 Testes em Dispositivos (Ambiente Real de Uso)

Os dispositivos foram selecionados para simular um ambiente de uso real e diversificado, utilizando equipamentos modernos e acessíveis.

| Dispositivo | Sistema Operacional | Processador / RAM | Navegador |
| :--- | :--- | :--- | :--- |
| **1. Smartphone** | Android 13 | Snapdragon 680, octa-core / 6 GB | Chrome 142+ |
| **2. Notebook (A)** | Ubuntu 24.04 LTS | Intel Core i5-13420H / 16 GB DDR5 | Chrome 142+ |
| **3. Notebook (B)** | Windows 11 | Intel Core i5-13420H / 16 GB DDR5 | Chrome 142+ |

---

### 🔎 Passo a Passo do Teste por Funcionalidade

1.  Abrir a plataforma **Khan Academy** no navegador Google Chrome 142+.
2.  Identificar e localizar a funcionalidade correspondente (de RF01 a RF16).
3.  Avaliar e registrar na planilha os seguintes itens para a funcionalidade:
    * **Implementada** (Sim/Não)
    * **Funcional** (Sim/Não)
    * **Observações** (Descrição de erros, comportamento inesperado, etc.)
    * **Dispositivo** (Qual foi usado: Smartphone, Notebook Ubuntu, Notebook Windows)
    * **Data e Horário**

---

### 📈 Análise e Classificação dos Dados

#### Cálculo da Métrica
A planilha Google Sheets calculará automaticamente o percentual, utilizando a seguinte fórmula:

$$\text{Métrica } 1.1 = \frac{\text{Nº de funcionalidades essenciais operacionais}}{\text{Nº total de funcionalidades essenciais esperadas}} \times 100$$

#### Classificação do Resultado

| Percentual | Avalição |
| :--- | :--- |
| 95% – 100% | Bom|
| 80% – 94% | Regular |
| < 80% |Insatisfatório|



---