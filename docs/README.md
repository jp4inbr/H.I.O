---
description: Essa página ira documentar todo o escopo do projeto
---

# 1.	Documento de Escopo

## **H.I.O (Hub de Inteligência Operacional)**

### <mark style="background-color:$info;">**||FICHA DE INSCRIÇÃO**</mark>&#x20;

<figure><img src=".gitbook/assets/image (2).png" alt="Grupo ANIMA Educação"><figcaption></figcaption></figure>

#### **Projeto A3 UC - Usabilidade e Desenvolvimento WEB**

**Professor: Mário Sergio Caldas Teixeira| E-mail: mariosct@prof.una.br / mariossct@ulife.com.br**\
**Campus: Center Minas | Turma: 439 | Turno: Noite | UC: UDS**<br>

<figure><img src=".gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>



<table data-search="false"><thead><tr><th width="342.60003662109375">Nome</th><th width="113.590576171875">RA</th><th width="319.99969482421875">E-Mail</th></tr></thead><tbody><tr><td>Arthur Justi Beiral</td><td>324122343</td><td>arthurbeiral@proton.me</td></tr><tr><td>Danilo Rubens da Silva Félix </td><td>325143953</td><td>rsdanillo13@gmail.com</td></tr><tr><td>João Vitor Paim Nicacio</td><td>32416402</td><td>joaovpaim2@gmail.com</td></tr><tr><td>Luís Henrique Ferreira Carneiro</td><td>324116351</td><td>luishenriquecarneiro20@gmail.com</td></tr><tr><td>Matheus Barreto Morgado</td><td>32420276</td><td>matheusbarretomorgado@gmail.com</td></tr><tr><td>Matheus Santos Damasceno</td><td>325115791</td><td>matheusdamasceno950@hotmail.com</td></tr><tr><td>Pedro Augusto Santos Nogueira</td><td>325128342</td><td>pedro.anogueira18@gmail.com</td></tr><tr><td>Thales Teichmann Valadares de Almeida</td><td>324133404</td><td>thales.teichmann@gmail.com</td></tr><tr><td>Yohanan Aguilar Amaral</td><td>324263860</td><td>yohan007aguilar@gmail.com</td></tr></tbody></table>

### &#xD;

### **|**<mark style="background-color:$info;">**|Proposta do Projeto**</mark>

### **|1. Introdução e Contextualização do Projeto**&#x20;

O projeto consiste no desenvolvimento de um sistema aplicado ao setor de Operações e Tecnologia da empresa. O propósito fundamental do software é centralizar, unificar e facilitar o acesso a ferramentas de automação e melhorias operacionais já existentes, criando uma interface amigável para que qualquer colaborador consiga executar suas tarefas diárias com facilidade.

#### **1.1. Identificação e Descrição do Problema**

* **Contexto e Impacto:** A empresa já possui scripts que automatizaram processos importantes, que agilizou a montagem de grupos de amostras. O gargalo atual é que os novos funcionários não possuem familiaridade com programação para executar esses scripts soltos. O impacto disso é a ineficiência no treinamento e a subutilização das automações.&#x20;
* **Evidências do Problema:** Outros colaboradores não conseguem manter os processos na ausência dos proprietários/desenvolvedores.
* **Relação com Padrões de USABILIDADE:** A dificuldade dos novos usuários fere os princípios de Usabilidade. Para resolver isso, o projeto focará principalmente na heurística de "Ajuda e documentação" (disponibilizando instruções claras no sistema) e no "Design estético e minimalista" (exibindo apenas as informações relevantes no dashboard). O sistema também buscará garantir eficácia, eficiência e satisfação ao usuário, pilares definidos pela norma ABNT NBR ISO 9241-11.

### **|2. Proposta de Solução do Grupo**

A proposta de desenvolvimento tecnológico do grupo é a confecção de um dashboard interativo e unificado. O objetivo geral deste software é servir como uma plataforma central onde o usuário poderá rodar todos os scripts operacionais (como relatórios e criação de grupos) a partir de botões e formulários simples. Dessa forma, aplicaremos os critérios de usabilidade para tornar a execução das tarefas diárias muito mais prática e acessível para novos usuários.

### **|3. Justificativa da Arquitetura (Web vs. Mobile)**

A plataforma adotada será uma Aplicação Web. Essa escolha se justifica pelos seguintes fatores:

* O contexto de uso e o perfil do usuário final indicam que as tarefas operacionais e o uso dos scripts atuais são realizados em computadores/notebooks corporativos durante o expediente de trabalho.
* Uma aplicação acessível por navegadores oferece alta facilidade de distribuição e manutenção, eliminando a necessidade de instalar programas ou ambientes de programação na máquina de cada novo funcionário.

### **|4. Mapeamento de Fontes de Pesquisa e Referências Bibliográficas**

Com base no objetivo de desenvolver uma plataforma WEB centralizadora (Dashboard de Operações e Tecnologia) para unificação de scripts legados, automação de processos e gestão das rotinas operacionais, identificou-se o seguinte mapeamento de práticas e tecnologias:

#### **4.1. Centralização de Plataforma e Interfaces Operacionais:**

* Centralização de Ferramentas e Portais Internos de Operações (Internal Developer/Operations Portals): Estudo de plataformas centralizadoras (como Backstage, Appsmith e Retool) que consolidam scripts, automações e rotinas dispersas em uma única interface WEB amigável, reduzindo o tempo de treinamento (onboarding) de novos colaboradores e eliminando a dependência da execução manual via terminal.
* Interfaces Amigáveis para Automação (Low-Code / No-Code Dashboards): Mapeamento de arquiteturas WEB de painéis operacionais que abstraem a complexidade do código subjacente, permitindo que usuários não técnicos executem fluxos de trabalho complexos, acompanhem o status de processamento e visualizem métricas de execução em tempo real.
* Arquitetura Web para Orquestração de Scripts Legados: Análise de padrões de integração entre front-end WEB e rotinas em background (scripts Python/APIs), garantindo que múltiplos utilitários isolados possam ser acionados de forma segura, padronizada e auditável através de uma aplicação central.
* Gestão do Conhecimento e Redução da Curva de Aprendizado no Onboarding: Benchmarking de soluções focadas na experiência do usuário interno (Employee Experience - EX), visando a padronização de interfaces para que a passagem de conhecimento para novos integrantes da equipe ocorra de forma intuitiva, minimizando erros operacionais e gargalos de treinamento.

#### **4.2. Tratamento de Dados e Automação de Processos Existentes:**

* Ingestão e ETL (Extract, Transform, Load): Pesquisa sobre conversão de arquivos brutos (.txt e .xlsx) em bases padronizadas para eliminar o erro humano de digitação.
* Auditoria de Conformidade (Cross-Checking): Cruzamento automático de dados de campo (matrizes, pontos, frequência, coordenadas GPS) com o Plano de Amostragem oficial.
* Processamento em Lote e Metadados: Inspeção interna de PDFs e processamento em lote (Batch Processing) para extração de amostras, eliminação de duplicatas e extração automatizada de mídias e metadados diretamente dos relatórios de campo.
* Integração de Relatórios de Equipamentos: Mapeamento das regras de leitura automatizada para calibração de equipamentos (RCE) e cruzamento de bases (PROCV) para relatórios de turbidez (NTU).

#### **Referências Bibliográficas (Normas ABNT):**

* WILSON, Charles; KIM, Gene. The DevOps Handbook: How to Create World-Class Agility, Reliability, and Security in Technology Organizations. 2nd ed. Portland: IT Revolution Press, 2021.
* VASWANI, Vikram. PHP & MySQL: novatos a profissionais. São Paulo: Alta Books, 2018.
* SWEIGART, Al. Automatize tarefas maçantes com Python: programação prática para iniciantes. São Paulo: Novatec Editora, 2015.
* SOMMERVILLE, Ian. Engenharia de software. 10. ed. São Paulo: Pearson Education do Brasil, 2019.
* RETOOL. Building Internal Tools: Architecture and Best Practices for Operations. San Francisco: Retool Inc., 2024. Disponível em: https://retool.com/. Acesso em: 8 set. 2026.
* PYTHON SOFTWARE FOUNDATION. pdfplumber / PyPDF2 / Pandas Documentation: Data Cleansing and PDF Processing. Disponível em: https://docs.python.org/3/library/. Acesso em: 9 set. 2026.
* PRESSMAN, Roger S.; MAXIM, Bruce R. Engenharia de software: uma abordagem profissional. 8. ed. Porto Alegre: AMGH, 2016.
* MONTGOMERY, Douglas C. Introdução ao controle estatístico da qualidade. 7. ed. Rio de Janeiro: LTC, 2016.
* MCKINNEY, Wes. Python para análise de dados: tratamento de dados com Pandas, NumPy e IPython. Tradução de Lúcia A. Kinoshita. São Paulo: Novatec Editora, 2018.
* GARTNER. Market Guide for Internal Developer Portals. Stamford: Gartner Research, 2023. Disponível em: https://www.gartner.com/. Acesso em: 8 set. 2026.
* CETESB. Guia nacional de coleta e preservação de amostras: água, sedimento, comunidades aquáticas e efluentes líquidos. São Paulo: CETESB; Brasília: ANA, 2011.
* CAMPOS, Vicente Falconi. Controle da qualidade total (no estilo japonês). 5. ed. Belo Horizonte: Editora INDG, 2014.
* AMERICAN PUBLIC HEALTH ASSOCIATION (APHA); AMERICAN WATER WORKS ASSOCIATION (AWWA); WATER ENVIRONMENT FEDERATION (WEF). Standard Methods for the Examination of Water and Wastewater. 23rd ed. Washington: APHA, 2017.
* ALUR, Deepak; CRUPI, John; MALKS, Dan. Core J2EE patterns: best practices and design strategies. 2nd ed. Upper Saddle River: Prentice Hall, 2003.

### **|5. Documentos**

* Documento das melhorias operacionais efetudas por funcionários da empresa

{% file src=".gitbook/assets/Melhorias Operacionais.pdf" %}
