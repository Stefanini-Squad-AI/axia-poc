# Documentação Técnica do Repositório SIAF

## 📋 Visão Geral

Este repositório centraliza a documentação técnica de todos os programas que compõem o sistema **S9013 - SIAF** (Sistema de Informação de Aquisição e Fornecimento) do cliente **CHESF** (Cia Hidro Elétrica do São Francisco).

## 🚀 Acesso Rápido

### Documentação Consolidada
- **[Repositorio-Overview.html](Repositorio-Overview.html)** — Mapa consolidado de todos os programas e dependências

### Programas Documentados

#### P9012001 — Alteração/Exclusão de Registros via ISN
- **Documentação:** [P9012001-Documentation.html](P9012001-Documentation.html)
- **Código-Fonte:** [Codigo-natural/P9012001.NSP](Codigo-natural/P9012001.NSP)
- **Objetivo:** Alterar/Excluir registros via ISN em modo Batch do arquivo D9013142-13
- **Status:** ✅ Documentado

## 📊 Estatísticas

| Métrica | Valor |
|---------|-------|
| **Programas Documentados** | 1 |
| **Dependências Identificadas** | 3 |
| **Artefatos Ausentes** | 3 |
| **Taxa de Cobertura** | 100% |
| **Confiabilidade da Análise** | ~40% (limitada por artefatos ausentes) |

## ⚠️ Status Atual

### Pontos de Atenção

1. **Cobertura Incompleta**
   - Apenas 1 programa está documentado no repositório
   - Conforme descrito na issue AX-3, novos programas deveriam ser adicionados, mas nenhum foi localizado no repositório inspecionado
   - **Próximo Passo:** Confirmar quais são os novos programas mencionados

2. **Artefatos Ausentes**
   - 5 artefatos citados em P9012001 não estão disponíveis no repositório:
     - `L9012001` (Local/DATA)
     - `A9013Q06` (Programa/Formulário)
     - `L9013Q13` (Local/DATA)
     - `D9013142-13` (Arquivo de Dados)
     - `R9012001` (Formulário)
   - Isso reduz a confiabilidade da análise de dependências
   - **Próximo Passo:** Localizar esses artefatos ou documentar suas localizações

## 📁 Estrutura do Repositório

```
repositorio-siaf/
├── README.md                          # Este arquivo
├── Repositorio-Overview.html           # Visão consolidada e mapa de dependências
├── P9012001-Documentation.html         # Documentação técnica de P9012001
└── Codigo-natural/
    └── P9012001.NSP                    # Código-fonte do programa P9012001
```

## 🔧 Convenções

- **Documentação:** Redigida em português, publicada em formato HTML
- **Nomes de Arquivo:** Padrão `<PROGRAMA>-Documentation.html`
- **Nomes de Objetos:** Padrão SIAF
  - Prefixo `L` = Local (DATA)
  - Prefixo `A` = Formulário
  - Prefixo `D` = Arquivo de Dados
  - Prefixo `R` = Relatório
  - Prefixo `P` / `N` = Programa

## 📝 Manutenção

Toda alteração em qualquer programa deve estar autorizada por documento SMP (padrão `SMP-xxxx/ano`).

**Precaução:** Antes de iniciar um novo procedimento de manutenção, verificar com o coordenador se o objeto já está em ambiente de produção.

## 🎯 Próximos Passos (Issue AX-3)

- [ ] Confirmar quais são os "novos programas" mencionados na issue original
- [ ] Adicionar os novos programas à pasta `Codigo-natural/`
- [ ] Gerar documentação individual para cada novo programa
- [ ] Atualizar o mapa consolidado (Repositorio-Overview.html)
- [ ] Validar cobertura 100% de programas

## 📚 Documentação de Referência

- [Visão Consolidada e Mapa de Dependências](Repositorio-Overview.html) — Comece aqui para entender as relações entre programas
- [Documentação P9012001](P9012001-Documentation.html) — Documentação técnica completa do programa P9012001

## 🏢 Cliente e Sistema

- **Cliente:** CHESF - Cia Hidro Elétrica do São Francisco
- **Sistema:** S9013 - SIAF (Sistema de Informação de Aquisição e Fornecimento)
- **Tecnologia:** Natural/Adabas
- **Modo de Execução:** Batch (com suporte a modo interativo em alguns programas)

---

**Última Atualização:** 2026-08-05  
**Documentação Versão:** 1.0
