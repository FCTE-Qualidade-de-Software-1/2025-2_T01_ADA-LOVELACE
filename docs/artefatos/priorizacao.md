# Quadro de Priorização

O Quadro de Priorização é uma ferramenta estratégica utilizada para organizar e priorizar funcionalidades baseadas no impacto na jornada do usuário. Esta metodologia ajuda a equipe a tomar decisões informadas sobre quais requisitos são mais críticos para as personas identificadas.

## Personas a serem avaliadas

- **Lucas (Ensino Médio)**: Estudante do 2º ano do ensino médio, com dificuldades em matemática e preparação para ENEM
- **Bia (Ensino Superior)**: Estudante universitária de Engenharia de Software, buscando certificações e conhecimento prático

Tanto o nível de impacto quanto o de importância serão avaliados de acordo com o fluxo básico do sistema.

## Níveis de Impacto

Os níveis de impacto representam o quanto a persona será impactada caso esses requisitos não sejam atendidos:

- **Baixo**: Pequeno incômodo no uso da plataforma
- **Médio**: Incomoda e pode chegar a comprometer o fluxo
- **Alto**: Impede o usuário de alcançar o objetivo

## Níveis de Importância

O nível de importância representa o quanto o requisito é essencial no produto final para ambos os usuários:

- **Médio**: Necessário para uma boa experiência de usuário
- **Alto**: Necessário para conclusão do fluxo
- **Crítico**: Necessário para o usuário alcançar o seu objetivo e por seguinte usar a aplicação

## Fluxo Básico do Sistema

O fluxo básico representa a jornada principal do usuário na plataforma:

1. **Acessa a plataforma**
2. **Verifica os cursos disponíveis**
3. **Se inscreve em um ou mais curso**
4. **Entra em um curso**
5. **Decisão**: Assistir aulas / Realizar atividades / Receber certificação

## Board com o Quadro de Priorização no Miro

<iframe width="768" height="432" src="https://miro.com/app/live-embed/uXjVJAhquoo=/?embedMode=view_only_without_ui&moveToViewport=-1239,1904,3289,1720&embedId=540057953147" frameborder="0" scrolling="no" allow="fullscreen; clipboard-read; clipboard-write" allowfullscreen></iframe>

## Análise de Impacto na Jornada do Usuário

| Requisitos | Cenário de ausência ou falha | Impacto (Lucas) | Impacto (Bia) | Nível de importância |
|------------|------------------------------|-----------------|---------------|---------------------|
| **RF01 - Visualizar aula em vídeo** | Aula não disponível em formato de vídeo, apenas em PDF ou Slides | **Alto**: Essencial para Lucas ver a aula em vídeo para aprender e se conectar com o conteúdo | **Alto**: Essencial para Bia ver a aula em vídeo tanto para melhor aprendizado quanto para acompanhar aulas durante transporte | **Crítico**: Para ambos, pode levar ao abandono da plataforma |
| **RF02 - Controlar velocidade do vídeo** | Controle de velocidade não disponível ou inexistente | **Baixo**: Lucas frequentemente tem dificuldade para acompanhar a explicação do professor | **Alto**: Para Bia, é importante acelerar as aulas pois não tem muito tempo | **Médio**: Pode tornar o fluxo de aprendizado de Bia lento |
| **RF03 - Acessar aulas offline** | Impossibilidade de baixar aulas | **Baixo**: Lucas assistirá aulas em casa onde o acesso à internet é constante | **Alto**: Bia frequentemente assistirá aulas durante tempo livre na universidade ou durante transporte | **Alto**: Pode impedir Bia de ter progresso constante |
| **RF04 - Monitorar progresso do curso** | Sem funcionalidade para acompanhar quantas aulas faltam | **Baixo**: Lucas perde motivação por não ver progresso claro | **Médio**: Bia não consegue planejar a conclusão de seus diversos cursos | **Médio**: Compromete a experiência impedindo progresso claro |
| **RF05 - Retomar de onde parou** | Sistema não salva o ponto exato da última visualização do vídeo | **Alto**: Lucas tem que procurar o ponto certo na timeline a cada acesso | **Alto**: Bia perde foco tendo que caçar o ponto de parada | **Crítico**: O tempo gasto procurando o ponto de parada atrasa o estudo de ambas as personas |
| **RF06 - Realizar exercícios** | Interface de teste/exercício falha ou não permite submeter resposta | **Alto**: Lucas não consegue praticar ou testar conhecimento, essencial para ele | **Alto**: Bia não consegue validar se absorveu o conteúdo | **Crítico**: Ambos usuários precisam colocar em prática o que aprenderam |
| **RF07 - Receber feedbacks dos exercícios** | Sistema apenas diz "Errado" sem explicar o porquê ou dar a resposta correta | **Médio**: Lucas precisa procurar a resposta no material, perdendo tempo | **Médio**: Bia precisa procurar a resposta no material, perdendo tempo | **Médio**: Ambas personas perdem tempo procurando a resposta |
| **RF08 - Submeter atividades** | Formulário de envio de projeto falha ao enviar arquivo, ou não existe | **Alto**: Para um estudante do ensino médio, a validação da escrita por outras pessoas é importante | **Médio**: Seria interessante ter correção de seus projetos ou códigos | **Alto**: Seria interessante para ambos usuários poder submeter atividades e projetos para correção |
| **RF09 - Postar dúvidas** | Sistema não tem campo para tirar uma dúvida específica | **Médio**: Seria interessante ter amparo da plataforma para tirar suas dúvidas | **Baixo**: Ela consegue tirar suas dúvidas pesquisando por conta própria por outras fontes | **Médio**: Ambos podem ficar confusos no meio do aprendizado |
| **RF10 - Pesquisar curso específico** | Campo de pesquisa de curso está inativo ou não existe | **Médio**: Pouparia tempo em meio a várias opções de curso | **Alto**: Facilitaria na busca em meio a tantos cursos | **Médio**: Apesar das poucas opções de cursos ofertados, um meio de busca facilitaria |
| **RF11 - Receber certificação** | Certificado não é gerado após conclusão do curso, ou não possui certificação | **Baixo**: Para Lucas o importante é passar na escola e estar preparado para provas de vestibular | **Alto**: Para Bia a certificação é o objetivo principal para aprimorar seu currículo | **Crítico**: Para Bia é crucial o certificado |
| **RF12 - Realizar simulados** | Sistema não apresenta simulados para provas específicas importantes | **Alto**: Lucas precisa simular o ENEM e outras provas de vestibular que pretende fazer | **Baixo**: Bia não está se preparando para nenhuma prova específica | **Alto**: Para Lucas é essencial avaliar seus conhecimentos para uma prova tão importante |
| **RF13 - Realizar avaliação de nivelamento** | Sistema não apresenta avaliação de nivelamento para saber o nível do aluno | **Alto**: Lucas precisa saber seu nível para começar a estudar na plataforma | **Baixo**: Bia está buscando conteúdos novos e ferramentas de aprendizado, então sempre começará do início | **Médio**: Para Lucas saber como está seu nível nas matérias básicas é relevante para saber onde começar |
| **RF14 - Gamificar experiência do usuário** | Não há medalhas, badges, pontos de experiência | **Alto**: Lucas se desmotiva. Ele é movido por recompensas e competição, o que ajuda na sua consistência diária | **Baixo**: Bia foca no conteúdo, mas ausência de sistema de progresso visual pode reduzir sutilmente o engajamento | **Médio**: Gamificar a plataforma ajuda na experiência do usuário |
| **RF15 - Acompanhar desempenho geral** | Não há relatórios sobre tempo de estudo, acertos em exercícios ou tópicos fracos do aluno | **Médio**: Lucas não consegue ver se está dedicando tempo suficiente e não sabe o que revisar | **Alto**: Bia depende de relatórios para otimizar estudo, focar em áreas fracas e gerenciar tempo de forma metódica | **Médio**: Transforma a visão geral em dados simples de visualização |
| **RF16 - Transcrição de áudio** | Transcrição existe, mas está cheia de erros, ou não existe | **Baixo**: Transcrição aumenta acessibilidade para pessoas com deficiência auditiva e torna conteúdo pesquisável | **Baixo**: Transcrição aumenta acessibilidade para pessoas com deficiência auditiva e torna conteúdo pesquisável | **Médio**: Transcrição ajuda no público alvo em geral, mas é essencial para público com deficiência auditiva |

## Metodologia

A priorização foi realizada através de uma **análise de impacto na jornada do usuário**, considerando:

1. **Identificação do Fluxo Básico**: Mapeamento da jornada principal do usuário
2. **Análise de Cenários de Ausência**: Avaliação do que acontece quando cada requisito não está disponível
3. **Impacto por Persona**: Avaliação específica do impacto para Lucas e Bia
4. **Classificação de Importância**: Definição do nível crítico de cada requisito

## Aplicação no Desenvolvimento

### Requisitos Críticos (Must Have)
- **RF01, RF05, RF06**: Essenciais para o funcionamento básico da plataforma
- **RF11**: Crítico para Bia (certificação)

### Requisitos de Alto Impacto (Should Have)
- **RF02, RF03, RF08, RF10, RF12, RF13**: Importantes para experiência otimizada
- **RF15**: Essencial para Bia (relatórios de desempenho)

### Requisitos de Médio Impacto (Could Have)
- **RF04, RF07, RF09, RF14, RF16**: Melhoram a experiência mas não são críticos

## Benefícios Gerais

A utilização desta metodologia de priorização proporciona:

- **Foco nas Necessidades Reais**: Priorização baseada no impacto real nas personas
- **Otimização de Recursos**: Desenvolvimento focado nos requisitos mais críticos
- **Melhoria da Experiência**: Entendimento claro de quais funcionalidades impactam mais os usuários
- **Tomada de Decisão Informada**: Base sólida para escolhas de desenvolvimento

## Tabela de Contribuição

| Matrícula | Nome completo                                 | Contribuição (%) |
| --------- | ----------------------------------------------| ---------------- |
| 222025950 | Mateus Henrique Queiroz Magalhães Sousa       | 16,7%            |
| 222006991 | Mateus Cavalcante Sousa                       | 16,7%            |
| 221008703 | Mateus Vieira Rocha da Silva                  | 16,7%            |
| 222026386 | Pedro Gois Marques Monteiro                   | 16,7%            |
| 221031363 | Renan Vieira Guedes                           | 16,7%            |
| 222021933 | William Bernardo da Silva                     | 16,7%            |

## Bibliografia


## 📝 Histórico de Versões

| Versão | Data       | Responsável | Alterações Realizadas                      |
| :----- | :--------- | :---------- | :----------------------------------------- |
| `1.0`    | 30/09/2025 | [Renan Vieira](https://github.com/R-enanVieira) | Adição do quadro de priorização |
