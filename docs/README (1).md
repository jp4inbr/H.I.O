# 1. Documento de Escopo

## 1. Objetivo geral

Reunir as rotinas de automação já existentes em uma única interface web, em que cada rotina vira um módulo com o mesmo padrão de uso:&#x20;

{% stepper %}
{% step %}
#### **Enviar entrada** &#x20;

O usuário envia um ou mais arquivos (PDF, XLSX ou CSV) arrastando e soltando ou selecionando pelo navegador. Antes da execução, o sistema valida o formato e os campos obrigatórios conforme o contrato do módulo. Se um arquivo for inválido, uma mensagem diz o que está errado e como corrigir. Cada rotina oferece o download do seu arquivo modelo de entrada. Em seguida, uma prévia mostra os arquivos enviados, e o usuário pode remover ou trocar arquivos sem precisar recomeçar.
{% endstep %}

{% step %}
#### **Executar**&#x20;

A rotina é disparada com um único botão. Durante o processamento, o sistema mostra o status da execução: em execução, concluída, concluída com ressalva, falhou ou cancelada. O usuário pode cancelar uma execução em andamento.
{% endstep %}

{% step %}
#### **Baixar resultado**

O resultado aparece sempre nas mesmas três zonas, na mesma ordem:&#x20;

* **Resumo** (cards de totais e alertas do que exige ação)&#x20;
* **Visualização principal** (definida por cada rotina)
* **Detalhe** (tabela completa, recolhida por padrão, com exportação para XLSX). Cada execução fica registrada no histórico, de onde é possível baixar novamente o resultado das execuções recentes.
{% endstep %}
{% endstepper %}

{% hint style="info" %}
Qualquer usuário novo deve executar uma rotina sozinho, sem treinamento e sem abrir terminal.
{% endhint %}

### **Relação com Padrões de Usabilidade**

A dificuldade dos usuários sem conhecimento técnico fere os princípios de usabilidade. O projeto adota 8 heurísticas de Nielsen, rastreadas nas telas do protótipo:

<table data-search="false"><thead><tr><th>Heurística</th><th>Tela do protótipo</th></tr></thead><tbody><tr><td>Prevenção de erros</td><td>Login / Início</td></tr><tr><td>Consistência e padrões</td><td>Função Principal</td></tr><tr><td>Visibilidade do status do sistema</td><td>Função Principal</td></tr><tr><td>Controle e liberdade do usuário</td><td>Função Principal (remover arquivos, cancelar); Configurações / Perfil</td></tr><tr><td>Ajuda e documentação</td><td>Função Principal (arquivo modelo)</td></tr><tr><td>Reconhecimento em vez de memorização</td><td>Tela de Ação da IA (Informe)</td></tr><tr><td>Ajudar os usuários a reconhecer, diagnosticar e recuperar erros</td><td>Resultado / Saída</td></tr><tr><td>Design estético e minimalista</td><td>Resultado / Saída</td></tr></tbody></table>

O sistema também busca garantir eficácia, eficiência e satisfação, pilares da norma ABNT NBR ISO 9241-11, com critérios de aceite definidos no RNF01:

* **Eficácia:** um usuário sem treinamento conclui qualquer rotina sozinho, sem ajuda.
* **Eficiência:** a execução, do painel até o resultado, leva até 5 minutos (sem contar o tempo de processamento).
* **Satisfação:** nota média ≥ 68 no questionário SUS (System Usability Scale).

## 2. Problema que o software resolve

As rotinas de automação já existentes são executadas hoje via terminal, Electron ou Streamlit. Para colaboradores sem conhecimento técnico, isso impede que executem as rotinas sozinhos, sem treinamento.

## 3. Público-alvo

Colaboradores operacionais e administrativos, incluindo aprendizes e trainees sem conhecimento técnico.

## 4. Funcionalidades principais

| Rotina                           | Entrada                                       | O que faz                                                       |
| -------------------------------- | --------------------------------------------- | --------------------------------------------------------------- |
| Conferência de Fichas            | Lote de PDFs de fichas                        | Extrai dados das imagens de cada ficha e aponta inconsistências |
| Verificação de Posição de Coleta | PDFs em lote + plano de amostragem (planilha) | Compara a posição declarada com a posição prevista no plano     |
| Sistema de Agendamentos          | Base do cliente (planilha)                    | Consolida os agendamentos e separa as confirmações pendentes    |

### **Funcionalidades da plataforma**

<details>

<summary><strong>1.Autenticação e perfis</strong></summary>

Login com usuário e senha; perfis Operador e Administrador.

</details>

<details>

<summary><strong>2.Painel de rotinas</strong></summary>

Rotinas disponíveis em cards, com nome e descrição curta.

</details>

<details>

<summary><strong>3.Envio e validação de entrada</strong></summary>

Envio de um ou mais arquivos por arrastar e soltar ou por seleção; validação do formato e dos campos obrigatórios antes da execução; download do arquivo modelo de entrada.

</details>

<details>

<summary><strong>4.Pré-visualização da entrada</strong></summary>

Prévia para confirmar antes de executar, com opção de remover ou trocar arquivos sem recomeçar.

</details>

<details>

<summary><strong>5.Resultado e download</strong></summary>

Resultado em três zonas (Resumo, Visualização principal e Detalhe com exportação para XLSX); textos gerados com botão de copiar.

</details>

<details>

<summary><strong>6.Histórico de execuções</strong></summary>

Registro de usuário, rotina, arquivo de entrada, data e hora, status e resumo estruturado; registros não editáveis; novo download do resultado das execuções recentes.

</details>

<details>

<summary><strong>7.Informe de IA</strong></summary>

Informe curto, gerado sob demanda a partir dos resumos estruturados das últimas execuções, apontando falhas, inconsistências recorrentes e rotinas com mais problemas.

</details>

### **Uso de IA**

* A **Conferência de Fichas** usa a IA para extrair os dados das fichas.

{% hint style="danger" icon="square-exclamation" %}
O **Informe de IA** usa apenas os resumos estruturados. A IA apenas lê e resume esses dados: não executa rotinas, não altera dados e não recebe os arquivos originais.
{% endhint %}

## 5. Limitações (escopo fora do projeto)

#### **Ficam fora do MVP (backlog):**

* Agendamento automático (cron)
* Notificações por e-mail
* Dashboard de ROI/telemetria
* Gestão de módulos pela interface
* Permissões por módulo
* Conformidade de acessibilidade (WCAG)
* Integração direta com SharePoint ou com o sistema do cliente. No MVP, as entradas tabulares (plano de amostragem e base do cliente) são enviadas por upload de arquivo.

{% hint style="info" %}
Restrição de compatibilidade: a interface funciona nos navegadores Chrome e Edge atuais, com prioridade para desktop.
{% endhint %}

## **6. Premissas do MVP**

| Item                                | Decisão                                                                            |
| ----------------------------------- | ---------------------------------------------------------------------------------- |
| Frontend                            | SPA web (React)                                                                    |
| Backend                             | API REST em Python (FastAPI), que executa as rotinas já existentes                 |
| Banco de dados                      | Relacional (SQLite no MVP, com migração futura para PostgreSQL)                    |
| IA                                  | API externa de LLM, consumida só pelo backend                                      |
| Rotinas do MVP                      | Conferência de Fichas, Verificação de Posição de Coleta e Sistema de Agendamentos  |
| Rotina de referência dos wireframes | Conferência de Fichas                                                              |

## 7. Justificativa da Arquitetura (Web vs. Mobile)

A plataforma adotada é uma **Aplicação Web**.

**Perfil do usuário final e contexto de uso** As tarefas operacionais e o uso das rotinas atuais são realizados em computadores/notebooks corporativos durante o expediente. A interface deve funcionar nos navegadores Chrome e Edge atuais, com prioridade para desktop.

**Portabilidade, hardware e acesso por navegador** Nenhum dos requisitos funcionais depende de recursos de hardware de dispositivos móveis. A aplicação acessada por navegador elimina a necessidade de instalar programas ou ambientes de programação na máquina de cada novo funcionário.

**Desempenho, escalabilidade e distribuição/manutenção**

* **Desempenho:** feedback visual de uma ação em até 1 s; navegação entre telas em até 2 s.
* **Extensibilidade:** uma nova rotina é integrada apenas implementando o padrão de módulo, sem alterar as telas existentes.
* **Distribuição:** SPA React entregue pelo Nginx, sob HTTPS, e API REST em FastAPI, hospedadas em uma VM do Google Cloud (Compute Engine). Banco de dados SQLite no MVP, com migração futura para PostgreSQL.

## 8. Mapeamento de Fontes de Pesquisa e Referências Bibliográficas

### 8.1. Fontes de Pesquisa e Mercado

**Centralização de Ferramentas e Portais Internos de Operações:** estudo de plataformas centralizadoras (como Backstage, Appsmith e Retool) que consolidam scripts, automações e rotinas dispersas em uma única interface web, reduzindo o tempo de treinamento (onboarding) de novos colaboradores e eliminando a dependência da execução manual via terminal.

**Interfaces Amigáveis para Automação:** mapeamento de painéis operacionais que abstraem a complexidade do código subjacente, permitindo que usuários não técnicos executem rotinas e acompanhem o status de processamento.

**Arquitetura Web para Orquestração de Rotinas Existentes:** análise de padrões de integração entre front-end web e rotinas em segundo plano (Python/API REST), garantindo que múltiplas rotinas possam ser acionadas de forma padronizada e registrada em histórico por meio de uma aplicação central.

**Gestão do Conhecimento e Redução da Curva de Aprendizado no Onboarding:** benchmarking de soluções focadas na experiência do usuário interno, visando a padronização de interfaces para que a passagem de conhecimento para novos integrantes da equipe ocorra de forma intuitiva.

### 8.2. Referências Bibliográficas (ABNT)

* NIELSEN, Jakob. Heurísticas de usabilidade. \[dados ABNT]
* SHNEIDERMAN, Ben. Regras de ouro do design de interfaces. \[dados ABNT]
* ASSOCIAÇÃO BRASILEIRA DE NORMAS TÉCNICAS. **ABNT NBR ISO 9241-11**. \[dados ABNT]
* INTERNATIONAL ORGANIZATION FOR STANDARDIZATION. **ISO/IEC 25010**. \[dados ABNT]
* System Usability Scale (SUS). \[dados ABNT]
* Documentação oficial: React; FastAPI; SQLite; Nginx; Google Cloud (Compute Engine, Cloud Storage, Cloud Logging); Vertex AI / Gemini. \[URL e data de acesso]
* Backstage; Appsmith; Retool. \[URL e data de acesso]

## 9. Documentos do trabalho

{% file src=".gitbook/assets/Melhorias Operacionais.pdf" %}
