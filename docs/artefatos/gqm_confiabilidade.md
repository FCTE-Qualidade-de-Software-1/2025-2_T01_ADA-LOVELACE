## Objetivo de Medição 1: Adequação funcional 

<div align="center">
  <table border="1" cellspacing="0" cellpadding="8" style="border-collapse: collapse; text-align: left;">
    <tr>
      <th><b>Analisar</b></th>
      <td>o Khan Academy</td>
    </tr>
    <tr>
      <th><b>Para o propósito de</b></th>
      <td>Avaliar</td>
    </tr>
    <tr>
      <th><b>Com respeito a</b></th>
      <td>Adequação funcional</td>
    </tr>
    <tr>
      <th><b>Do ponto de vista da</b></th>
      <td>Comunidade de estudantes </td>
    </tr>
    <tr>
      <th><b>No contexto da</b></th>
      <td>Disciplina de Qualidade de Software 1 (FCTE - UnB)</td>
    </tr>
  </table>
</div>



<div align="center">
  <font size="4"><figcaption>Tabela 1: Objetivo de Medição: Adequação funcional</figcaption></font>
</div>

---

### Perguntas e Hipóteses de Medição

Para decompor o objetivo de análise da Adequação funcional, foram formuladas as seguintes perguntas e hipóteses.

**Questão 1: Completude funcional**
> o Khan Academy tem as funcionalidades necessárias para atender as necessidades dos estudantes?

* **Hipótese 1.1 (H1.1):** Pelo menos 85% das funcionalidades  utilizadas pelos estudantes estarão implementadas e operacionais no sistema.

**Questão 2: Corretude funcional**
> As funcionalidades estão implementadas de forma correta?

* **Hipótese 2.1 (H2.1):** Pelo menos 90% dos casos de uso para estudantes serão executados corretamente, sem apresentar falhas ou erros.

**Questão 3: Apropriação funcional**

> As funcionalidades implementadas são realmente úteis?

* **Hipótese 3.1 (H3.1):** Todas as funcionalidades classificadas anteriormente como críticas serão atendidas.

---

### Seleção das Métricas

**Questão 1: Completude funcional**

* **Métrica 1.1: Cobertura de Funcionalidades Essenciais**
    * **Definição:** Percentual de funcionalidades essenciais (prioritárias para estudantes) que estão implementadas e operacionais no sistema.
    * **Fórmula:**  `(Nº de funcionalidades essenciais disponíveis / Nº total de funcionalidades essenciais esperadas) * 100`
    * **Coleta:** 
        1. Identificar e listar as funcionalidades essenciais para estudantes.
        2. Verificar no sistema se cada funcionalidade está implementada e funcionando corretamente.
        3. Contar o número de funcionalidades essenciais disponíveis e o total esperado.
        4. Aplicar a fórmula para validar a **H1.1**.
    * **Pontuação de Julgamento:** 

        | **Excelente** | **Bom** | **Regular** | **Insatisfatório** |
        |:--------------:|:--------:|:-------------:|:-------------------:|
        | ≤ 1 bug/KLOC | >1 e ≤3 bugs/KLOC | >3 e ≤6 bugs/KLOC | >6 bugs/KLOC |

    * **Propósito:** Identificar se as áreas mais críticas do sistema são também as que concentram mais defeitos reportados.

* **Métrica 1.2: Percentual de Commits de Correção**

    * **Definição:** Percentual de **commits** cuja mensagem contém palavras-chave como "fix", "corrige" ou "bugfix".
    * **Fórmula:** `(Número de commits de correção / Número total de commits) * 100`
    * **Coleta:**
        1. Definir um período de análise (ex: últimos 24 meses).
        2. Contar o número total de commits com `git log --oneline | wc -l`
        3. Contar o número de commits de correção com `git log --grep="fix\|bugfix\|corrige\|correção\|hotfix" --regexp-ignore-case --oneline | wc -l.`
        4. Aplicar a fórmula para validar a **H1.2**.

    * **Pontuação de Julgamento:** 

        | **Excelente** | **Bom** | **Regular** | **Insatisfatório** |
        |:--------------:|:--------:|:-------------:|:-------------------:|
        | ≤ 10% | >10% e ≤20% | >20% e ≤35% | >35% |

    * **Propósito:** Avaliar se o esforço de desenvolvimento é mais reativo (corrigindo falhas) do que proativo (desenvolvendo novas funcionalidades).

**Questão 2: Tolerância a Falhas**

* **Métrica 2.1: Índice de Tratamento de Exceções**

    * **Definição:** Percentual de operações de I/O críticas que estão contidas dentro de um bloco de tratamento de exceções (`try-catch`).
    * **Fórmula:** `(Número de operações críticas com try-catch / Número total de operações críticas) * 100`
    * **Coleta:** Revisão manual de código ou uso de scripts de análise estática para buscar padrões de tratamento de exceções.
        1. Definir a lista de "operações críticas": chamadas de função/método para conexão com banco de dados ex:( `new PDO(`, `pg_connect`), manipulação de arquivos (ex: `fopen`, `file_put_contents`) etc.
        2. Nos diretórios dos módulos priorizados, executar scripts de busca (`grep` ou `ack`) para contar o número total de ocorrências dessas operações.
        3. Executar um segundo script para contar quantas dessas ocorrências estão sintaticamente dentro de um bloco `try { ... }`.
        4. Aplicar a fórmula para validar a **H2.1**.
    * **Pontuação de Julgamento:** 

        | **Excelente** | **Bom** | **Regular** | **Insatisfatório** |
        |:--------------:|:--------:|:-------------:|:-------------------:|
        | ≥ 90% | 70%–89% | 40%–69% | < 40% |

    * **Propósito:** Medir a robustez do código contra erros em tempo de execução.

**Questão 3: Recuperabilidade**

* **Métrica 3.1: Análise Qualitativa de Código de Backup**

    * **Definição:** Avaliação qualitativa, baseada em um checklist estruturado, das rotinas de backup para verificar sua compreensibilidade, documentação e aderência a boas práticas.
    * **Coleta:** Inspeção manual do código-fonte das funcionalidades de backup.
        1. Identificar os arquivos/módulos responsáveis pela funcionalidade de backup/restauração no código-fonte.
        2. Realizar uma inspeção manual do código aplicando o checklist abaixo. Cada item recebe uma nota de 0 (ausente) a 2 (excelente).
        3. Checklist de Análise:
            * **Documentação (Comentários):** O código possui comentários explicando a lóǵica geral e os passos críticos?
            * **Clareza do Código:** Os nomes de variáveis e funções são intuitivos e seguem um padrão?
            * **Tratamento de Erros:** O código verifica falhas potenciais (ex: falha de escrita em disco, permissões) e as reporta de forma adequada?
            * **Configuração:** As configurações críticas (ex: caminhos de backup, credenciais) são externalizadas e não "hard-coded"?
            * **Testabilidade:** A estrutura do código permite a criação de testes unitários ou de integração?
        4. A pontuação final (0 a 10) será a soma dos pontos do checklist, usada para validar a **H3.1**.

    * **Pontuação de Julgamento:** 

        | **Excelente** | **Bom** | **Regular** | **Insatisfatório** |
        |:--------------:|:--------:|:-------------:|:-------------------:|
        | 9–10 | 7–8 | 4–6 | 0–3 |

    * **Propósito:** Avaliar a manutenibilidade e a confiabilidade percebida dos mecanismos de recuperação de dados do ponto de vista de um desenvolvedor.

### Critérios para Julgamento

* **Aceitável:** ≥ 70% das métricas classificadas como "Bom" ou "Excelente". O sistema demonstra robustez e previsibilidade.
* **Parcialmente aceitável:** Entre 40% e 69% das métricas com nível "Regular" ou superior. O sistema funciona, mas pode apresentar instabilidades pontuais.
* **Inaceitável:** > 30% das métricas atingindo o nível "Insatisfatório". A estabilidade do sistema é considerada crítica e propensa a falhas.

---

### Relação entre a Confiabilidade, Perguntas e Métricas


<div align="center">
  <table border="1" cellspacing="0" cellpadding="8" style="border-collapse: collapse; text-align: left;">
    <tr>
      <th><b>Questão</b></th>
      <th><b>Métricas Simplificadas</b></th>
      <th><b>Tipo de Coleta</b></th>
    </tr>
    <tr>
      <td><b>Maturidade</b><br>Qual é a estabilidade do código em relação a defeitos?</td>
      <td>
        - Densidade de defeitos (issues "bug" por KLOC)<br>
        - Percentual de commits de correção (mensagens com fix/corrige/bugfix)
      </td>
      <td>
        - GitHub issues + contagem de linhas com cloc (ou similar)<br>
        - Histórico de commits via git log com filtros/regex
      </td>
    </tr>
    <tr>
      <td><b>Tolerância a Falhas</b><br>Qual é o nível de robustez contra falhas em tempo de execução?</td>
      <td>
        - Índice de tratamento de exceções (% operações I/O críticas dentro de try-catch)
      </td>
      <td>
        - Análise estática / scripts (grep/ack) para localizar operações críticas e verificar blocos try-catch<br>
        - Revisão manual de trechos críticos quando necessário
      </td>
    </tr>
    <tr>
      <td><b>Recuperabilidade</b><br>Qual é a eficácia dos mecanismos de recuperação de dados?</td>
      <td>
        - Pontuação qualitativa das rotinas de backup (checklist, escala 0–10)
      </td>
      <td>
        - Inspeção manual do código e documentação aplicando checklist de avaliação (documentação, clareza, tratamento de erros, configuração, testabilidade)
      </td>
    </tr>
  </table>

  <div style="margin-top: 8px; text-align: center;">
    <font size="4"><figcaption>Tabela 2: Questões e Métricas Simplificadas</figcaption></font>
  </div>
</div>

---

### Diagrama GQM - Confiabilidade (Representação Estrutural)

![Relação entre a Confiabilidade, Perguntas e Métricas](../assets/diagrama_confiabilidade.png)

<div style="margin-top: 8px; text-align: center;">
  <font size="4"><figcaption>Figura 2: Diagrama GQM - Confiabilidade. Autor: <a href="http://github.com/manuvaladares">Manuela Valadares</a></figcaption></font>
</div>