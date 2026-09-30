# ⚙️ H.I.O - Hub de Inteligência Operacional

> **Status do Projeto:** Em Desenvolvimento (Fase: RT02 - Engenharia de Requisitos, Arquitetura e Prototipagem)

## Sobre o Projeto
**H.I.O. (Hub de Inteligência Operacional)** é uma plataforma web centralizada para automação e auditoria de dados. O sistema integra 11 pipelines de processamento de arquivos (PDFs, imagens e texto) em um dashboard inteligente, convertendo rotinas operacionais manuais em fluxos de trabalho escaláveis e orientados a dados.

Este projeto faz parte da Unidade Curricular de Usabilidade e Desenvolvimento Web (Projeto A3 - Una).

## Funcionalidades Principais

| Rotina | Entrada | O que faz |
| :--- | :--- | :--- |
| **Conferência de Fichas** | Lote de PDFs de fichas | Extrai dados das imagens de cada ficha e aponta inconsistências. |
| **Verificação de Posição de Coleta** | PDFs em lote + plano de amostragem (planilha) | Compara a posição declarada com a posição prevista no plano. |
| **Sistema de Agendamentos** | Base do cliente (planilha) | Consolida os agendamentos e separa as confirmações pendentes. |

## Estrutura do Repositório
O projeto está organizado na seguinte arquitetura de pastas:

```text
/
├── backend/       # Código fonte da API, serviços de automação e integração com IA
├── frontend/      # Código fonte da interface do usuário (Dashboard)
├── docs/          # Documentação técnica e artefatos de engenharia (RTs)
├── .editorconfig  # Padronização de formatação de código entre as IDEs
└── .gitignore     # Ignora arquivos de sistema e pastas de dependências
