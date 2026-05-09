# Grupo 02 — Estudo Técnico Preliminar (ETP)

## Módulo do Sistema

Análise técnica do DFD: cotação de preços (via Banco de Preços), especificação refinada e análise de mercado.

## Responsabilidade

- Receber DFD consolidado (G01)
- Consultar Banco de Preços para obter 3+ cotações por item
- Refinar especificação técnica (normas, padrões, garantias)
- Gerar ETP com recomendações de parcelamento

**Entradas:** DFD (G01)  
**Saídas:** ETP com cotações, especificação e análise de mercado

---

## Entregas Mínimas

| Artefato | Descrição |
|----------|-----------|
| Casos de uso (mínimo 4) | Consultar Banco de Preços, fazer cotação, validar especificação, gerar ETP |
| Diagrama UML de classes | `Cotacao`, `Fornecedor`, `Especificacao`, `AnaliseETP` |
| Diagrama de sequência | Integração com Banco de Preços, análise de propostas |
| BPMN | Fluxo de análise técnica com pontos de validação |
| Backlog | Mínimo 5 histórias de usuário |
| ADRs (mínimo 2) | Ex.: API vs. manual para Banco de Preços, critérios de seleção de fornecedores |
| Testes | Validação de cotações, detecção de outliers de preço |
| Auditoria | Quem fez cada cotação, critério de seleção |

---

## Interfaces com Outros Módulos

- **Entrada ← G01 (DFD):** DFD consolidado
- **Saída → G03 (Atas SRP):** ETP
- **Saída → G04 (TR):** ETP

---

## Entrega do Grupo

> Preencha esta seção ao finalizar:

- **Integrantes:**
- **Data de entrega:**
- **Branch/PR:**

---

## 📋 O que entregar

### Artefato: Um arquivo `.md` por Caso de Uso (mínimo 6 UCs)

Cada arquivo deve seguir o template abaixo e cobrir os casos de uso mais críticos identificados no contexto do sistema.

**UCs obrigatórios** (baseados nos gargalos do domínio):

| Arquivo | Caso de Uso |
|---------|-------------|
| `UC-01-registrar-demanda.md` | Registrar Demanda de Material/Serviço |
| `UC-02-consolidar-dfd.md` | Consolidar Demandas em DFD |
| `UC-03-realizar-cotacao.md` | Realizar Cotação de Preços |
| `UC-04-elaborar-tr.md` | Elaborar Termo de Referência |
| `UC-05-emitir-ordem-fornecimento.md` | Emitir Ordem de Fornecimento |
| `UC-06-gerenciar-ata-srp.md` | Gerenciar Ata de Registro de Preços |

---

## 📄 Template de Especificação

```markdown
# UC-XX — [Nome do Caso de Uso]

## Identificação

| Campo | Valor |
|-------|-------|
| **ID** | UC-XX |
| **Nome** | |
| **Ator Principal** | |
| **Atores Secundários** | |
| **Prioridade** | Alta / Média / Baixa |
| **Origem** | [cite requisito, artefato de origem ou RN-XX] |

## Descrição Resumida

> (1-2 frases descrevendo o objetivo do UC)

## Pré-condições

- (o que deve ser verdadeiro antes do UC iniciar)

## Pós-condições

### Sucesso
- (estado do sistema após conclusão bem-sucedida)

### Fracasso
- (estado do sistema se o UC falhar)

## Fluxo Principal (Caminho Feliz)

| Passo | Ator | Ação |
|-------|------|------|
| 1 | [Ator] | ... |
| 2 | [Sistema] | ... |
| 3 | [Ator] | ... |

## Fluxos Alternativos

### FA-01: [Nome do fluxo alternativo]
- **Condição de ativação**: (quando este fluxo ocorre)
- **A partir do passo**: X
- **Passos**:
  1. ...
  2. ...
- **Retorno ao fluxo principal**: passo Y / encerramento

## Fluxos de Exceção

### FE-01: [Nome da exceção]
- **Condição**: (o que causa esta exceção)
- **Tratamento**:
  1. ...
- **Resultado**: (cancelamento / retry / notificação)

## Regras de Negócio Aplicáveis

- RN-XX: [descrição curta]

## Requisitos Não-Funcionais Relevantes

- (desempenho, segurança, etc., se houver)

## Wireframe / Esboço de Tela (opcional)

> (descrição textual ou esboço ASCII da interface esperada)
```

---

## 🛠️ Ferramentas Recomendadas

| Ferramenta | Uso | Link |
|-----------|-----|------|
| **Markdown** | Formato dos arquivos | Qualquer editor de texto |
| **VS Code** | Editor com preview MD | [code.visualstudio.com](https://code.visualstudio.com) |
| **Obsidian** | Editor MD com tabelas | [obsidian.md](https://obsidian.md) |
| **Typora** | Editor WYSIWYG para MD | [typora.io](https://typora.io) |

> 💡 **Dica**: Leia o contexto do sistema com atenção aos verbos de ação — cada ação descrita pode ser um passo de um fluxo.

---

## 📁 Estrutura esperada da pasta

```
grupo-02-especificacao-uc/
├── README.md                        ← este arquivo (preencha a seção abaixo)
├── UC-01-registrar-demanda.md
├── UC-02-consolidar-dfd.md
├── UC-03-realizar-cotacao.md
├── UC-04-elaborar-tr.md
├── UC-05-emitir-ordem-fornecimento.md
└── UC-06-gerenciar-ata-srp.md
```

---

## ✏️ Seção de Entrega (preencher pelo grupo)

**Integrantes:**
- ...

**Decisões tomadas:**
> ...

**Limitações identificadas:**
> ...
