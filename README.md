# H.I.O. - Hub de Inteligência Operacional

Status do Projeto: Em Desenvolvimento (Fase: RT02 - Engenharia de Requisitos, Arquitetura e Prototipagem)

## Sobre o Projeto
O H.I.O. (Hub de Inteligência Operacional) é uma plataforma web centralizada para automação e auditoria de dados. O objetivo geral é reunir rotinas de automação já existentes em uma única interface web, onde cada rotina atua como um módulo com um padrão de uso uniforme.

Problema resolvido: Atualmente, as rotinas de automação são executadas via terminal, Electron ou Streamlit. Isso cria uma barreira técnica e impede que colaboradores operacionais e administrativos (como aprendizes e trainees sem conhecimento em programação) executem as rotinas sozinhos e sem treinamento prévio. A aplicação acessada por navegador elimina a necessidade de instalar programas ou ambientes de desenvolvimento nas máquinas corporativas.

Este projeto integra a Unidade Curricular de Usabilidade e Desenvolvimento Web (Projeto A3 - Una).

## Padrão de Uso (Fluxo do Usuário)
Qualquer novo usuário consegue executar uma rotina de forma autônoma através de três passos padronizados:

1. Enviar entrada: Upload de arquivos (PDF, XLSX, CSV) via drag-and-drop ou seleção. O sistema valida formato e campos obrigatórios. Erros geram mensagens claras de correção. Há suporte a preview e download de arquivos modelo.
2. Executar: Disparo em botão único. Exibição de status em tempo real (em execução, concluída, concluída com ressalva, falhou, cancelada) com possibilidade de cancelamento ativo.
3. Baixar resultado: O painel de saída é dividido em três zonas fixas:
   - Resumo: Cards de totais e alertas de ação.
   - Visualização principal: Gráficos ou painéis específicos da rotina.
   - Detalhe: Tabela completa exportável (XLSX). O histórico de execuções recentes fica salvo para download posterior.

## Funcionalidades e Escopo do MVP
O sistema integra pipelines de processamento de arquivos. As rotinas definidas para o Minimum Viable Product (MVP) são:

| Rotina | Entrada | O que faz |
| :--- | :--- | :--- |
| Conferência de Fichas | Lote de PDFs de fichas | Extrai dados das imagens de cada ficha e aponta inconsistências |
| Verificação de Posição de Coleta | PDFs em lote + plano de amostragem (planilha) | Compara a posição declarada com a posição prevista no plano |
| Sistema de Agendamentos | Base do cliente (planilha) | Consolida os agendamentos e separa as confirmações pendentes |

Regras de Uso de IA:
- A rotina de "Conferência de Fichas" utiliza IA (LLM) para extrair os dados diretamente das imagens/PDFs.
- O recurso "Informe de IA" utiliza apenas os resumos estruturados. A IA atua de forma passiva, apenas lendo e resumindo dados: ela não executa rotinas, não altera dados e não tem acesso aos arquivos originais.

## Arquitetura e Stack Tecnológica
A plataforma foi concebida como uma Aplicação Web (Desktop-first), compatível com Chrome e Edge.

- Frontend: SPA web desenvolvida em React, entregue via Nginx sob HTTPS.
- Backend: API REST em Python (FastAPI), responsável pela execução em background das rotinas existentes.
- Banco de Dados: Relacional estruturado em SQLite (MVP), com arquitetura preparada para migração para PostgreSQL.
- Inteligência Artificial: API externa de LLM (ex: Vertex AI / Gemini), consumida exclusivamente via backend.
- Infraestrutura: Hospedagem em VM no Google Cloud Platform (Compute Engine).

Requisitos de Desempenho: O feedback visual para o usuário ocorrerá em até 1 segundo, e a navegação entre telas não ultrapassará 2 segundos. O design modular permite acoplar novas rotinas sem alterar a interface existente.

## Princípios de Usabilidade e UX
O projeto é guiado pelas heurísticas de usabilidade e pelas normas de qualidade de software, sanando o déficit atual de acessibilidade técnica.

Heurísticas de Jakob Nielsen rastreadas no protótipo:
| Heurística | Tela do Protótipo (Aplicação) |
| :--- | :--- |
| Prevenção de erros | Login / Início |
| Consistência e padrões | Função Principal |
| Visibilidade do status do sistema | Função Principal |
| Controle e liberdade do usuário | Função Principal (remover arquivos, cancelar) e Configurações/Perfil |
| Ajuda e documentação | Função Principal (fornecimento de arquivo modelo) |
| Reconhecimento em vez de memorização | Tela de Ação da IA (Informe) |
| Diagnóstico e recuperação de erros | Resultado / Saída |
| Design estético e minimalista | Resultado / Saída |

Critérios de Aceite NBR ISO 9241-11 (RNF01):
- Eficácia: O usuário sem treinamento conclui qualquer rotina sozinho, sem ajuda.
- Eficiência: A execução, desde o painel até a geração do resultado, leva até 5 minutos (excluindo tempo de processamento em nuvem).
- Satisfação: Nota média >= 68 no questionário SUS (System Usability Scale).

## Limitações (Fora do Escopo MVP)
Os seguintes itens compõem o backlog e não estarão presentes no lançamento do MVP:
- Agendamento automático (cron).
- Notificações automáticas por e-mail.
- Dashboard administrativo de ROI e telemetria.
- Gestão de módulos e atribuição de permissões de acesso pela interface.
- Conformidade completa com diretrizes de acessibilidade (WCAG).
- Integração direta com SharePoint ou sistemas de terceiros (entradas dependem de upload manual).

## Estrutura do Repositório e Gestão de Código
Para garantir escalabilidade, o repositório adota práticas sólidas de engenharia (Clean Code / SOLID):

- Estrutura Organizacional: Repositório particionado em `/frontend`, `/backend` e `/docs`.
- Proteção de Branch: A branch main bloqueia commits diretos. As integrações exigem Pull Request e code review.
- Padronização: Implementação de `.editorconfig` e Linters para formatação universal, independentemente da IDE.
- Padrão de Commits: Utilização obrigatória do Conventional Commits (feat, fix, docs, style, refactor, test).
- Versionamento Documental: Integração contínua (Git Sync) entre o repositório e o GitBook do projeto.

## Referências e Benchmarking
- ABNT NBR ISO 9241-11 e ISO/IEC 25010.
- NIELSEN, Jakob. Heurísticas de usabilidade.
- SHNEIDERMAN, Ben. Regras de ouro do design de interfaces.
- Avaliação System Usability Scale (SUS).
- Documentação Técnica: React, FastAPI, SQLite, Nginx, Google Cloud, Vertex AI/Gemini.
- Benchmarking de Ferramentas de Orquestração: Backstage, Appsmith e Retool.

## Equipe do Projeto
- Arthur Justi & SYF: Arquitetura de Software
- Danilo R.: UI/UX & Prototipagem
- João Vitor: GitBook e Documentação
- Luís Carneiro: Planejamento e Cronograma (Trello)
- Matheus Damasceno: Product Vision Board
- Matheus Morgado & Thales: Engenharia de Requisitos
- Yohanan Aguilar: Gestão de Qualidade de Código (QA)
