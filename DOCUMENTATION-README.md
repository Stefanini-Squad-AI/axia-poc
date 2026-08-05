# Documentação Técnica do Repositório SIAF S9013

## 📋 Visão Geral

Este repositório contém a documentação técnica completa de todos os programas Natural do sistema SIAF S9013 (Sistema de Informação de Aquisição e Fornecimento) da CHESF (Cia Hidro Elétrica do São Francisco).

**Objetivo:** Permitir que analistas de manutenção entendam, avaliem impacto e mantenham programas sem necessidade de ler código-fonte diretamente.

---

## 📚 Estrutura de Documentação

### Nível 1: Visão Geral (Este arquivo)
- **Arquivo:** `DOCUMENTATION-README.md`
- **Conteúdo:** Guia de navegação, estrutura, responsabilidades
- **Público:** Todos

### Nível 2: Índice de Programas
- **Arquivo:** `REPOSITORY-OVERVIEW.html`
- **Conteúdo:** Lista de todos os programas, consolidação de dependências, matriz de compartilhamento
- **Público:** Analistas, Gestores
- **Quando usar:** Primeira consulta; buscar um programa; entender relacionamentos gerais

### Nível 3: Mapa de Dependências
- **Arquivo:** `DEPENDENCY-MAP.html`
- **Conteúdo:** Análise profunda de dependências diretas/inversas, impacto de mudanças, recomendações
- **Público:** Arquitetos, Analistas de Impacto, Programadores
- **Quando usar:** Antes de alterar um programa ou objeto; análise de cascata de falhas; planejamento de mudanças

### Nível 4: Documentação Completa por Programa
- **Arquivo:** `<PROGRAMA>-Documentation.html` (ex: `P9012001-Documentation.html`)
- **Conteúdo:** 14 seções padronizadas (resumo executivo, fluxo, inventário, regras de negócio, riscos, modernização, etc.)
- **Público:** Todos (conforme necessidade)
- **Quando usar:** Compreender completamente um programa; validar regras de negócio; planejar refatoração

---

## 🗂️ Programas Documentados

| Programa | Status | Seções | Documentação | Link |
|----------|--------|--------|--------------|------|
| P9012001 | ✅ Documentado | 14/14 | Completa | [P9012001-Documentation.html](P9012001-Documentation.html) |

**Total:** 1 programa | **Taxa de Cobertura:** 100% | **Versão:** 1.0

---

## 🎯 Como Usar Esta Documentação

### Cenário 1: Entender o que faz um programa

1. Acesse `REPOSITORY-OVERVIEW.html`
2. Navegue até "Programas do Repositório"
3. Clique no programa desejado
4. Consulte a seção "Resumo Executivo" (Seção 1) da documentação do programa

**Tempo esperado:** 5-10 minutos

### Cenário 2: Avaliar impacto de uma mudança

1. Acesse `DEPENDENCY-MAP.html`
2. Navegue até "Matriz de Dependências Diretas"
3. Identifique todas as dependências do programa/objeto a ser alterado
4. Para cada dependência, consulte "Análise de Impacto por Objeto"
5. Documente risco e ações necessárias
6. Consulte documentação completa de cada programa afetado (Seções 9, 11, 13)

**Tempo esperado:** 30-60 minutos por programa alterado

### Cenário 3: Planejar testes de regressão

1. Acesse documentação completa do programa modificado
2. Consulte Seção 3 (Fluxo de Execução) para entender logicamente programa
3. Consulte Seção 9 (Regras de Negócio) para casos de teste
4. Consulte Seção 11 (Problemas e Riscos) para cenários de falha
5. Consulte Seção 5 (Mapa de Dependências) para identificar programas dependentes a testar
6. Crie plano de teste baseado em cenários críticos

**Tempo esperado:** 1-2 horas

### Cenário 4: Adicionar novo programa ao repositório

1. Desenvolva programa em `Codigo-natural/`
2. Crie arquivo `<NOVO_PROGRAMA>-Documentation.html` usando P9012001 como template
3. Preencha as 14 seções com informações específicas do novo programa
4. Atualize `REPOSITORY-OVERVIEW.html`:
   - Adicione entrada em "Programas do Repositório"
   - Atualize dashboard (total de programas, taxa de cobertura)
   - Atualize "Dependências de P9012001" se aplicável
5. Atualize `DEPENDENCY-MAP.html`:
   - Adicione novo programa em "Matriz de Dependências Diretas"
   - Mapeie todas as dependências do novo programa
   - Identifique dependências inversas (que programas dependem do novo)
   - Atualize "Mapa de Objetos Compartilhados"
6. Submeta PR para revisão

**Tempo esperado:** 4-6 horas (2h análise + 2-4h documentação)

---

## 📖 Seções Padrão de Documentação (14 total)

Cada programa é documentado em 14 seções padronizadas para permitir comparação direta:

| # | Seção | Propósito | Público |
|---|-------|----------|---------|
| 1 | Resumo Executivo | O quê, quem, quando, objetivo | Gerentes, Analistas |
| 2 | Resumo Técnico | Plataforma, linguagem, métricas | Arquitetos, Técnicos |
| 3 | Fluxo de Execução | Passo-a-passo, lógica | Programadores, QA |
| 4 | Inventário de Objetos | Lista completa de dependências | Analistas, DBA |
| 5 | Mapa de Dependências | Quem/o quê depende | Analistas de Impacto |
| 6 | Grafo de Chamadas | Profundidade de chamadas | Programadores |
| 7 | Matriz CRUD | Operações por tabela/arquivo | DBA, Dados |
| 8 | Mapa de Impacto | Quem depende deste programa | Analistas de Impacto |
| 9 | Regras de Negócio | Validações, decisões (BR-*) | Analistas de Negócio |
| 10 | Performance | Operações críticas, gargalos | Arquitetos, Performance |
| 11 | Problemas e Riscos | Bugs, riscos (P-*, RO-*, RS-*, RM-*) | Todos |
| 12 | Refatoração | Oportunidades de melhoria | Arquitetos, Programadores |
| 13 | Estratégia de Modernização | Candidatura, roadmap, ROI | Gestores, Arquitetos |
| 14 | Artefatos Ausentes | Limitações, confiança | Todos |

---

## 🔍 Convenções de Nomenclatura

- **Programas:** `P<número>` (ex: P9012001, P9012002)
- **Documentação:** `<PROGRAMA>-Documentation.html` na raiz
- **Código-fonte:** `Codigo-natural/<ARQUIVO>.NSP`
- **LDAs (Local Data Area):** `L<número>` ou `A<número>` (compartilhada)
- **Formulários:** `R<número>` (Report/Formulário)
- **Arquivos Adabas:** `D<número>` (Data file)
- **Regras de Negócio:** `BR-<número>` (ex: BR-001, BR-002)
- **Problemas:** `P-<número>`, `RO-<número>`, `RS-<número>`, `RM-<número>`

---

## ⚠️ Artefatos Críticos Ausentes

O repositório atualmente **não contém** os seguintes artefatos necessários para análise completa:

| Artefato | Tipo | Impacto | Status |
|----------|------|--------|--------|
| L9012001 | LDA | Estrutura de entrada não confirmada | ❌ Não encontrado |
| A9013Q06 | LDA | Interface com N9013Q06 não confirmada | ❌ Não encontrado |
| L9013Q13 | LDA | Propósito desconhecido | ❌ Não encontrado |
| D9013142-13 | Arquivo Adabas | Estrutura não confirmada | ❌ Não encontrado |
| N9013Q06 | Programa | Lógica de validação não documentada | ❌ Não encontrado |
| R9012001 | Formulário | Formato de saída desconhecido | ❌ Não encontrado |

**Confiabilidade Atual:**
- ✅ 75% confiável para análise técnica (fluxo, validação)
- ⚠️ 50% confiável para análise de impacto (dependências, regras)

**Ação Recomendada:** Recuperar ou documentar estes artefatos para aumentar confiança

---

## 📋 Checklist para Adicionar Novo Programa

- [ ] Programa implementado em `Codigo-natural/<PROGRAMA>.NSP`
- [ ] Arquivo HTML `<PROGRAMA>-Documentation.html` criado com 14 seções
- [ ] Seção 1: Resumo Executivo preenchido
- [ ] Seção 2: Resumo Técnico preenchido (plataforma, métricas)
- [ ] Seção 3: Fluxo de Execução documentado (diagrama, passo-a-passo)
- [ ] Seção 4: Inventário de Objetos completo
- [ ] Seção 5: Mapa de Dependências preenchido
- [ ] Seção 6: Grafo de Chamadas documentado
- [ ] Seção 7: Matriz CRUD preenchida
- [ ] Seção 8: Mapa de Impacto preenchido
- [ ] Seção 9: Regras de Negócio documentadas (BR-001, BR-002, etc.)
- [ ] Seção 10: Performance analisada
- [ ] Seção 11: Problemas e Riscos documentados
- [ ] Seção 12: Refatoração identificada
- [ ] Seção 13: Estratégia de Modernização proposta
- [ ] Seção 14: Artefatos Ausentes listados
- [ ] `REPOSITORY-OVERVIEW.html` atualizado (dashboard, programas, índice)
- [ ] `DEPENDENCY-MAP.html` atualizado (matriz, análise, recomendações)
- [ ] Documentação revisada por Arquiteto
- [ ] Documentação validada por DBA/Operações
- [ ] PR criado com referência à issue correspondente

---

## 🔄 Fluxo de Manutenção de Documentação

### Quando Alterar um Programa

**Sequência de Responsabilidades:**

1. **Programador:** Altera código em `Codigo-natural/<PROGRAMA>.NSP`
   - Commit com mensagem referenciando SMP-<número>/ano ou issue

2. **Programador/Analista Técnico:** Atualiza comentários do código
   - Indicar novo número SMP ou referência de mudança
   - Descrever o quê mudou e por quê

3. **Analista Técnico:** Atualiza documentação HTML
   - Seção 3: Fluxo de Execução (se lógica mudou)
   - Seção 4: Inventário de Objetos (se dependências mudaram)
   - Seção 5: Mapa de Dependências (se novos objetos usados)
   - Seção 9: Regras de Negócio (se validações mudaram)
   - Seção 11: Problemas e Riscos (se novos riscos identificados)

4. **Gestor/Coordenador:** Atualiza `REPOSITORY-OVERVIEW.html`
   - Data de última alteração
   - Documento SMP de autorização

5. **QA:** Atualiza Seção 10 (Performance) e Seção 11 (Riscos) se impactado por testes
   - Novos gargalos identificados
   - Novos casos de falha descobertos

6. **Todos:** Documentação é revisada antes de merge

### Quando Adicionar Novo Programa

Vide checklist acima.

### Quando Recuperar Artefato Ausente

1. Localizar artefato (LDA, arquivo, programa)
2. Validar com equipe legacy (se disponível)
3. Atualizar Seção 4 (Inventário de Objetos) do programa afetado
4. Atualizar Seção 14 (Artefatos Ausentes) — marcar como "✅ Recuperado"
5. Revisar e atualizar Seção 5 (Dependências) com informações confirmadas
6. Revisar análise de impacto e risco, atualizando confiança

---

## 👥 Responsabilidades

| Papel | Responsabilidade |
|------|-----------------|
| **Programador** | Escrever código; manter comentários atualizados; indicar SMP |
| **Analista Técnico** | Manter documentação HTML de programa (seções 1-8, 12-14) |
| **Analista de Negócio** | Manter Seção 9 (Regras de Negócio) de cada programa |
| **Arquiteto** | Revisar Seção 13 (Modernização); manter REPOSITORY-OVERVIEW.html |
| **DBA/Operações** | Manter Seção 7 (CRUD), Seção 10 (Performance), Seção 11 (Riscos) |
| **QA** | Validar documentação de testes; reportar novos riscos |
| **Gestor** | Aprovar mudanças; garantir conformidade com SMP; atualizar datas |

---

## 📞 Suporte e Contato

**Dúvidas sobre documentação?**

1. Consulte `REPOSITORY-OVERVIEW.html` (Seção 8: "Referência Rápida")
2. Consulte `DEPENDENCY-MAP.html` para análise de impacto
3. Consulte documentação específica do programa (`<PROGRAMA>-Documentation.html`)
4. Contate o Analista Técnico ou Arquiteto responsável

**Encontrou erro ou inconsistência?**

1. Abra uma issue com tag `documentation`
2. Reference o arquivo e seção específica
3. Descreva o erro ou inconsistência
4. O Analista Técnico revisará e corrigirá

---

## 📊 Status e Histórico de Alterações

| Data | Versão | Mudança | Responsável |
|------|--------|---------|------------|
| 2026-08-05 | 1.0 | Criação inicial; documentação de P9012001 | Analista Técnico |

---

## 📝 Notas Importantes

⚠️ **Esta documentação é tão importante quanto o código.**

- Toda alteração de código deve ser acompanhada de atualização de documentação
- Revisar documentação antes de tomar decisões críticas (modernização, alterações de banco)
- Usar documentação como base para treinamento de novas pessoas na equipe
- Manter histórico de alterações (SMP, autor, data) para rastreabilidade

---

## 🎓 Recursos Adicionais

- [Análise Completa de P9012001](P9012001-Documentation.html) — Documentação modelo com 14 seções
- [Índice de Programas](REPOSITORY-OVERVIEW.html) — Visão consolidada de todos os programas
- [Mapa de Dependências](DEPENDENCY-MAP.html) — Análise de impacto e relacionamentos

---

**© CHESF/Stefanini - Confidencial**

*Última atualização: 2026-08-05*
