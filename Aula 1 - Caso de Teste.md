## O que são Casos de Teste?

**Casos de teste** são documentos que descrevem os testes a serem realizados em um sistema, especificando as condições, entradas, passos e resultados esperados. Eles são usados para validar que o sistema está funcionando corretamente e atendendo aos requisitos.

### Estrutura de um Caso de Teste

Um caso de teste deve conter as seguintes informações:

1. **ID do Caso de Teste**  
   Um identificador único para o caso de teste.

2. **Descrição**  
   Uma breve descrição do que o teste deve verificar.

3. **Pré-condições**  
   O que deve ser verdadeiro ou o que precisa ser configurado antes de executar o teste.

4. **Entradas**  
   Os dados que serão fornecidos ao sistema para o teste.

5. **Passos**  
   Os passos detalhados para executar o teste.

6. **Resultado Esperado**  
   O que deve acontecer quando o teste for executado corretamente.

7. **Resultado Real**  
   O que realmente aconteceu ao executar o teste (registrado durante a execução).

8. **Status do Teste**  
   O resultado do teste: **Passou** ou **Falhou**.

---

## Exemplo de Casos de Teste para o Aplicativo TaskMaster

Aqui estão os casos de teste para as funcionalidades **Adicionar Tarefa**, **Editar Tarefa**, **Excluir Tarefa** e **Visualizar Tarefas**.

### Casos de Teste em Markdown


# Casos de Teste - TaskMaster

## 1. Caso de Teste: Adicionar Tarefa
- **ID**: CT01
- **Descrição**: Verificar se o usuário consegue adicionar uma nova tarefa corretamente.
- **Pré-condições**: O aplicativo está aberto e o usuário está na tela de adicionar tarefa.
- **Entradas**: 
  - Título da tarefa: "Comprar leite"
  - Descrição da tarefa: "Ir até o mercado e comprar leite"
- **Passos**:
  1. Na tela de tarefas, clicar no botão "Adicionar Tarefa".
  2. Preencher o título e a descrição da tarefa.
  3. Clicar no botão "Salvar".
- **Resultado Esperado**: A tarefa "Comprar leite" deve aparecer na lista de tarefas com a descrição correta.
- **Resultado Real**: [Preenchido após execução do teste]
- **Status do Teste**: [Passou/Falhou]

---

## 2. Caso de Teste: Editar Tarefa
- **ID**: CT02
- **Descrição**: Verificar se o usuário consegue editar uma tarefa existente.
- **Pré-condições**: O aplicativo está aberto e o usuário tem uma tarefa existente na lista.
- **Entradas**:
  - Tarefa a ser editada: "Comprar leite"
  - Novo título: "Comprar leite e pão"
  - Nova descrição: "Ir ao mercado, comprar leite e pão"
- **Passos**:
  1. Na tela de tarefas, clicar na tarefa "Comprar leite".
  2. Clicar no ícone de edição.
  3. Alterar o título para "Comprar leite e pão" e a descrição para "Ir ao mercado, comprar leite e pão".
  4. Clicar no botão "Salvar".
- **Resultado Esperado**: A tarefa deve ser atualizada para "Comprar leite e pão" com a nova descrição.
- **Resultado Real**: [Preenchido após execução do teste]
- **Status do Teste**: [Passou/Falhou]

---

## 3. Caso de Teste: Excluir Tarefa
- **ID**: CT03
- **Descrição**: Verificar se o usuário consegue excluir uma tarefa corretamente.
- **Pré-condições**: O aplicativo está aberto e o usuário tem uma tarefa existente na lista.
- **Entradas**:
  - Tarefa a ser excluída: "Comprar leite"
- **Passos**:
  1. Na tela de tarefas, clicar na tarefa "Comprar leite".
  2. Clicar no ícone de exclusão.
  3. Confirmar a exclusão.
- **Resultado Esperado**: A tarefa "Comprar leite" deve ser removida da lista de tarefas.
- **Resultado Real**: [Preenchido após execução do teste]
- **Status do Teste**: [Passou/Falhou]

---

## 4. Caso de Teste: Visualizar Tarefas
- **ID**: CT04
- **Descrição**: Verificar se o usuário consegue visualizar todas as tarefas na lista.
- **Pré-condições**: O aplicativo está aberto e o usuário tem várias tarefas adicionadas.
- **Entradas**: Não se aplica (apenas visualizar).
- **Passos**:
  1. Na tela de tarefas, navegar até a lista de tarefas.
  2. Verificar se todas as tarefas aparecem corretamente com seus títulos e descrições.
- **Resultado Esperado**: Todas as tarefas devem ser exibidas corretamente na lista.
- **Resultado Real**: [Preenchido após execução do teste]
- **Status do Teste**: [Passou/Falhou]


---

## Explicação dos Casos de Teste

1. **Adicionar Tarefa (CT01)**: Este caso de teste verifica se o usuário consegue adicionar uma nova tarefa com sucesso. O teste envolve interagir com o formulário de entrada de dados e salvar a tarefa.

2. **Editar Tarefa (CT02)**: Este caso testa a funcionalidade de edição de uma tarefa existente. O teste garante que as alterações feitas na tarefa sejam salvas corretamente.

3. **Excluir Tarefa (CT03)**: Este caso verifica se o usuário consegue excluir uma tarefa corretamente. O objetivo é garantir que a tarefa seja removida da lista de tarefas.

4. **Visualizar Tarefas (CT04)**: Este caso de teste verifica se o usuário consegue visualizar corretamente todas as tarefas na lista. Isso ajuda a garantir que o aplicativo mostre as tarefas salvas de maneira adequada.

---

### Como Criar Casos de Teste

1. **Identificação do Caso de Teste**: Comece com um identificador único para cada caso de teste. Isso facilita o rastreamento.

2. **Descrição do Teste**: Descreva claramente o que você está testando. A descrição deve ser direta e objetiva.

3. **Pré-condições**: Defina o que precisa ser verdadeiro antes de realizar o teste (por exemplo, o usuário precisa estar logado, ou um formulário deve estar disponível).

4. **Entradas**: Quais dados ou informações são necessários para o teste.

5. **Passos**: Liste cada ação que o testador deve executar para completar o teste. Seja detalhado.

6. **Resultado Esperado**: Especifique o que deve ocorrer após a execução do teste. O que será considerado um sucesso.

7. **Resultado Real e Status**: Após executar o teste, registre o que realmente aconteceu e marque se o teste passou ou falhou.

---

Esses casos de teste são exemplos simples, mas a ideia é que você os crie de acordo com os requisitos do sistema, garantindo que cada funcionalidade importante seja verificada de forma sistemática e clara.


---

# 📌 Documentação de Resultados dos Casos de Teste

## 📖 Introdução
Após a execução de um caso de teste, é fundamental documentar os resultados para garantir rastreabilidade e acompanhamento do desempenho do sistema. Essa documentação pode ser feita no próprio documento de casos de teste ou em um relatório separado, dependendo da complexidade do projeto e das práticas da equipe de QA (Quality Assurance), ou Garantia da Qualidade.

---

## 📌 Onde Documentar os Resultados?

- **No próprio documento de casos de teste**: Quando os testes são simples e não necessitam de um acompanhamento extenso.
- **Em um documento separado (Relatório de Execução de Testes)**: Quando há um grande volume de testes ou quando a análise detalhada dos erros e evidências se faz necessária.

---

## 📌 Como Documentar os Resultados dos Testes

Cada caso de teste deve ter um campo para registrar os resultados da execução. A estrutura básica inclui:

1. **Resultado Real**: O que realmente aconteceu ao executar o teste.
2. **Status do Teste**:
   - ✅ **Passou**: O resultado real corresponde ao esperado.
   - ❌ **Falhou**: O resultado real difere do esperado.
3. **Evidências**: Capturas de tela, logs ou outras informações que possam ser úteis.
4. **Comentários**: Notas adicionais para análise, incluindo causas possíveis e sugestões de correção.

---

## 📌 Exemplo de Documentação no Documento de Casos de Teste


# Casos de Teste - Aplicativo TaskMaster

## 1. Caso de Teste: Adicionar Tarefa
- **ID**: CT01
- **Descrição**: Verificar se o usuário consegue adicionar uma nova tarefa corretamente.
- **Pré-condições**: O aplicativo está aberto e o usuário está na tela de adicionar tarefa.
- **Entradas**:
  - Título da tarefa: "Comprar leite"
  - Descrição da tarefa: "Ir ao mercado e comprar leite"
- **Passos**:
  1. Na tela de tarefas, clicar no botão "Adicionar Tarefa".
  2. Preencher o título e a descrição da tarefa.
  3. Clicar no botão "Salvar".
- **Resultado Esperado**: A tarefa "Comprar leite" deve aparecer na lista de tarefas com a descrição correta.

### 📌 Resultado da Execução
- **Resultado Real**: A tarefa foi adicionada corretamente e apareceu na lista de tarefas.
- **Status**: ✅ Passou
- **Evidências**: ![Captura de tela](caminho_para_imagem.png)
- **Comentários**: Teste realizado no Android 12, sem erros encontrados.


---

## 📌 Exemplo de Relatório de Execução de Testes Separado

Se a equipe optar por um documento separado, ele pode ser estruturado assim:


# 📋 Relatório de Execução de Testes - Aplicativo TaskMaster

## 🗓️ Data da Execução: 31/01/2025
## 👤 Testador: João Silva
## 🏷️ Versão Testada: 1.2.0

### 🔹 Resumo dos Testes
| ID do Caso | Descrição                   | Status  | Evidência              | Comentários |
|-----------|-----------------------------|---------|------------------------|-------------|
| CT01      | Adicionar Tarefa            | ✅ Passou | [Ver imagem](#)        | Teste sem erros |
| CT02      | Editar Tarefa               | ❌ Falhou | [Ver imagem](#)        | Botão "Salvar" não funciona |
| CT03      | Excluir Tarefa              | ✅ Passou | [Ver imagem](#)        | Ok |

### 🔹 Análise das Falhas
- **CT02 - Editar Tarefa**
  - **Erro encontrado**: O botão "Salvar" não responde ao clique.
  - **Impacto**: Usuário não pode editar tarefas.
  - **Recomendação**: Reportar bug para a equipe de desenvolvimento e retestar após correção.


---

## 📌 Conclusão
A documentação dos resultados dos testes é essencial para garantir um histórico detalhado da qualidade do software. Escolher entre registrar os resultados no próprio documento de casos de teste ou em um relatório separado depende do contexto do projeto. O mais importante é manter as informações organizadas e acessíveis para facilitar correções e melhorias no sistema.

