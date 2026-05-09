# Grupo 04 — Elaboração de Termo de Referência (TR)

## Módulo do Sistema

Compilação do ETP com as regras da Lei Complementar nº 123/2006 para geração do Termo de Referência (documento formal).

## Responsabilidade

- Receber ETP (G02) e decisão de ata (G03)
- Aplicar regras da Lei 123/2006:
  - Itens ≤ R$ 80k: exclusivo para ME/EPP
  - Itens > R$ 80k: 25% exclusivo para ME/EPP, 75% para todos
  - Empate ficto: ME/EPP tem vantagem de até 10% de diferença
- Compilar TR com especificação, divisão de cotas, prazos e critérios de aceitação

**Entradas:** ETP (G02), Decisão de Ata (G03)  
**Saídas:** TR formatado e validado

---

## Entregas Mínimas

| Artefato | Descrição |
|----------|-----------|
| Casos de uso (mínimo 4) | Compilar ETP em TR, calcular cotas, validar Lei 123, gerar TR |
| Diagrama UML de classes | `TermoReferencia`, `CotaExclusiva`, `CotaAberta`, `RegrasLei123`, `Criterio` |
| Diagrama de sequência | Compilação e validação de conformidade legal |
| BPMN | Fluxo de TR com validações jurídicas obrigatórias |
| Backlog | Mínimo 5 histórias de usuário |
| ADRs (mínimo 2) | Ex.: qual versão da Lei 123 aplicar? Como lidar com atualizações? |
| Testes | Cálculo correto de cotas, validação de percentuais |
| Auditoria | Versão da Lei aplicada, quem validou, data de criação |

---

## Interfaces com Outros Módulos

- **Entrada ← G02 (ETP):** ETP
- **Entrada ← G03 (Atas SRP):** Decisão de ata
- **Saída → G05 (Mapa de Riscos):** TR
- **Saída → G06 (Edital):** TR

---

## Entrega do Grupo

> Preencha esta seção ao finalizar:

- **Integrantes:**
- **Data de entrega:**
- **Branch/PR:**

---

## 📋 O que entregar

### Artefatos: Um diagrama por fluxo (mínimo 4)

| Arquivo | Fluxo |
|---------|-------|
| `SEQ-01-coleta-demandas.png` + fonte | Coleta e consolidação de demandas no DFD |
| `SEQ-02-cotacao-precos.png` + fonte | Realização de cotação via Banco de Preços |
| `SEQ-03-emitir-ordem-fornecimento.png` + fonte | Emissão de OF com rastreamento |
| `SEQ-04-envio-prefeitura.png` + fonte | Envio do processo à Prefeitura via 1doc |

---

## 🔍 O que cada diagrama deve mostrar

### SEQ-01: Coleta e Consolidação de Demandas
- Secretaria registra demanda no sistema
- Sistema notifica Almoxarifado
- Almoxarifado verifica estoque
- Almoxarifado consolida em DFD
- Sistema verifica regra de fracionamento (RN-03)
- DFD é aprovado e encaminhado ao setor de Compras

### SEQ-02: Cotação de Preços
- Chefe de Licitações inicia cotação para um item
- Sistema consulta Banco de Preços (externo)
- Banco de Preços retorna preços de processos anteriores
- Sistema sugere valor médio de referência
- Usuário valida / ajusta valor
- Sistema registra cotação associada ao ETP

### SEQ-03: Emissão de Ordem de Fornecimento
- Chefe de Compras seleciona item da Ata SRP
- Sistema verifica validade da ata
- Sistema verifica se quantidade solicitada ≤ saldo da ata
- Usuário preenche OF
- Sistema gera OF numerada
- Sistema notifica Contabilidade (empenho pendente)
- Sistema atualiza saldo da ata

### SEQ-04: Envio do Processo à Prefeitura
- Processo completo (DFD + ETP + TR) aprovado internamente
- Jurídico interno valida e assina
- Sistema empacota documentos
- Sistema envia via 1doc à Prefeitura
- Prefeitura confirma recebimento e autua o processo
- Sistema registra número de autuação

---

## 🛠️ Ferramentas Recomendadas

| Ferramenta | Link | Observação |
|-----------|------|------------|
| **PlantUML** | [plantuml.com](https://plantuml.com) | Melhor para diagramas de sequência textuais |
| **SequenceDiagram.org** | [sequencediagram.org](https://sequencediagram.org) | Online, simples, exporta PNG |
| **Mermaid** | [mermaid.live](https://mermaid.live) | Integra com GitHub |
| **draw.io** | [app.diagrams.net](https://app.diagrams.net) | Alternativa visual |

### Exemplo PlantUML — Sequência básica:

```plantuml
@startuml SEQ-01-coleta-demandas
title Coleta e Consolidação de Demandas

actor "Secretaria" as SEC
participant "Sistema" as SIS
actor "Almoxarifado" as ALM
database "Banco de Dados" as DB

SEC -> SIS: registrarDemanda(itens, justificativa)
SIS -> DB: salvar(Demanda)
DB --> SIS: Demanda salva
SIS -> ALM: notificar(novaDemanda)

ALM -> SIS: consultarEstoque(itens)
SIS -> DB: buscarEstoque(itens)
DB --> SIS: saldoEstoque
SIS --> ALM: saldoEstoque

alt Item sem estoque suficiente
  ALM -> SIS: consolidarNoDFD(item)
else Item com estoque
  ALM -> SIS: marcarComoAtendido(item)
end

ALM -> SIS: fecharDFD()
SIS -> DB: atualizarStatus(DFD, CONSOLIDADO)
SIS --> ALM: DFD consolidado com sucesso
@enduml
```

---

## 📁 Estrutura esperada da pasta

```
grupo-04-diagramas-sequencia/
├── README.md
├── SEQ-01-coleta-demandas.puml
├── SEQ-01-coleta-demandas.png
├── SEQ-02-cotacao-precos.puml
├── SEQ-02-cotacao-precos.png
├── SEQ-03-emitir-ordem-fornecimento.puml
├── SEQ-03-emitir-ordem-fornecimento.png
├── SEQ-04-envio-prefeitura.puml
└── SEQ-04-envio-prefeitura.png
```

---

## ✏️ Seção de Entrega (preencher pelo grupo)

**Integrantes:**
- ...

**Decisões tomadas:**
> ...

**Limitações identificadas:**
> ...
