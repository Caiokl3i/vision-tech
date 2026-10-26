# Projeto Prático Integrado de Segurança da Informação — 2º Bimestre

## 1. Visão Geral e Objetivo

O objetivo deste projeto é vivenciar na prática os dois lados da Segurança da Informação: a **segurança defensiva (Blue Team)** e a **segurança ofensiva (Red Team)**.

Ao longo do 2º bimestre, cada equipe projetará e colocará em execução um sistema web corporativo e, ao mesmo tempo, atuará na identificação, exploração, monitoramento e mitigação de vulnerabilidades no sistema de uma equipe rival.

---

## 2. Estrutura das Equipes e Dinâmica de Confronto

- **Formação da Turma:** 6 grupos de aproximadamente 4 alunos.
- **Pares de Confronto Direto (Fixos):**
  - **Confronto A:** Grupo 1 vs. Grupo 2
  - **Confronto B:** Grupo 3 vs. Grupo 4
  - *(Confronto C: Grupo 5 vs. Grupo 6)*

- **Duplo Papel em Sala:** Durante as sessões práticas em laboratório, cada equipe operará em duas frentes simultâneas:
  - **2 Alunos (Foco Blue Team):** Responsáveis pelo monitoramento de logs em tempo real, aplicação de regras de firewall, sustentação e mitigação de incidentes.
  - **2 Alunos (Foco Red Team):** Responsáveis pela execução de varreduras, exploração de falhas web, testes de estresse (DDoS) e engenharia social contra o alvo rival.

---

## 3. Cenários de Empresas Fictícias (Sorteio/Atribuição)

Cada grupo desenvolverá o sistema para uma das empresas abaixo, garantindo um contexto de negócio real e proteção de dados sensíveis:

- **Grupo 1 — Ótica VisionTech (Comércio & Saúde):** Sistema de gestão de clientes e prescrições médicas de lentes (grau, histórico e exames).
- **Grupo 2 — PetShop Patas & Pelos (Serviços):** Sistema de agendamento de consultas, histórico clínico de pets e cadastro de tutores.
- **Grupo 3 — E-Commerce ElectroHub (Varejo Eletrônico):** Plataforma de venda de componentes, cadastro de clientes, fornecedores e histórico de pedidos.
- **Grupo 4 — E-Commerce Moda & Estilo (Varejo de Vestuário):** Loja virtual de roupas com dados de clientes, endereços de entrega e catálogo de fornecedores.
- **Grupo 5 — Logística MoverExpress (Transporte & Cargas):** Sistema de rastreamento de frotas, rotas de entrega e cadastro de motoristas (CNH, CPF).
- **Grupo 6 — CargoConnect Logística (Armazenamento):** Gestão de galpões logísticos, inventário de mercadorias de terceiros e contratos corporativos.

---

## 4. Requisitos Mínimos da Aplicação (Blue Team)

### 1. Autenticação e Controle de Acesso (RBAC):
- Tela de Login e Logout funcional.
- Mínimo de 3 níveis de permissão: **Administrador**, **Operador/Funcionário** e **Cliente/Usuário Comum**.

### 2. Banco de Dados Populado:
- Banco de dados estruturado com no **mínimo 50 registros válidos e coerentes com o segmento da empresa**.
- O sistema deve armazenar e gerenciar os dados dos usuários e senhas de forma segura.

### 3. Superfície da Aplicação:
- Painel administrativo restrito para consulta e gestão dos registros.
- Pelo menos um formulário com busca ou inserção de dados.
- Funcionalidade de upload de arquivo (ex: foto de perfil ou comprovante).

### 4. Infraestrutura e Registros:
- Aplicação rodando em ambiente isolado (Máquina Virtual ou Contêiner Docker no laboratório).
- **Geração de Logs Ativa:** Registros de acessos e erros do servidor web e banco de dados habilitados para análise do Blue Team.

### 5. Falhas:
- Seu sistema deve ter uma falha "proposital" que não será divulgada, mas assim que descoberta pelo outro time deverá ser corrigida.

---

## 5. Vetores de Ataque Permitidos (Red Team)

A equipe de ataque estará autorizada a explorar os seguintes vetores no IP/Ambiente do rival:

- **Técnicas de Web Hacking:** Injeção de SQL (SQLi), Bypassing de Autenticação/Autorização, Cross-Site Scripting (XSS) e Upload Inseguro de Arquivos.
- **Engenharia Social (\*):** Criação e envio de **até 2 e-mails de Phishing/Spoofing** simulando a interface do sistema rival para tentar capturar as credenciais da conta do professor.
- **Exploração de Credenciais Vazadas:** Análise e exploração de pacotes de dados vazados (*dumps*) disponibilizados pelo professor durante a simulação de Dark Web.
- **Ataques de Negação de Serviço (DDoS / Teste de Carga):** Disparo de requisições massivas para testar a resiliência da infraestrutura rival.

---

## 6. Regras de Engajamento (Rules of Engagement)

> [!CAUTION]
> **ATENÇÃO:** O descumprimento de qualquer uma das regras abaixo implicará na desclassificação sumária da equipe no projeto.

1. **Restrição de Alvo:** É estritamente proibido atacar qualquer IP, servidor ou dispositivo fora da Máquina Virtual designada para o grupo rival.
2. **Engenharia Social Restrita:** Disparos de Phishing são permitidos exclusivamente para a conta corporativa/acadêmica do Professor (`marcelo.franca@ifms.edu.br`). Proibido ataques contra e-mails ou redes pessoais de alunos.
3. **Limite do SLA de Disponibilidade:** Ataques de negação de serviço (DDoS) só poderão ser executados durante os horários de aula autorizados em laboratório.
4. **Sigilo de Vulnerabilidades:** As falhas descobertas no sistema rival não devem ser compartilhadas até o término do desafio.

---

## 7. Cronograma Semanal do Projeto

| Semana | Fase do Projeto | Atividades Práticas e Entregáveis |
| :---: | :--- | :--- |
| **Semana 1** | **Apresentação e Alinhamento** | Apresentação das regras, divisão dos 6 grupos, sorteio das empresas fictícias e definição dos pares de confronto. |
| **Semana 2** | **Desenvolvimento do Sistema** | Implementação da estrutura web, modelagem do banco de dados e povoação dos 50 usuários. Configuração das permissões (RBAC). |
| **Semana 3** | **Hardening e Deploy** | Subida do serviço em VM/Docker local. Cadastro obrigatório da conta do Professor (`marcelo.franca@ifms.edu.br`). Ativação dos arquivos de log. |
| **Semana 4** | **Reconhecimento (Gray Box)** | Liberação dos IPs entre as equipes rivais. O Red Team inicia a varredura de portas e enumeração de rotas. Envio de uma credencial de usuário comum para o rival. |
| **Semana 5** | **Execução de Ataques e Phishing** | Aula Prática em Lab: Red Team tenta exploração de vulnerabilidades web e envio dos 2 e-mails de Phishing ao Professor. Blue Team monitora logs de rede e aplica bloqueios de IP. |
| **Semana 6** | **Credenciais Vazadas e DDoS** | Simulação de Dark Web: Liberação de um arquivo de credenciais vazadas pelo professor. O Red Team busca acessos elevados; simultaneamente, executa testes de estresse (DDoS). SLA do Blue Team: restaurar o serviço em até 10 minutos. |
| **Semana 7** | **Mitigação e Patching** | O Blue Team analisa os logs e relatórios preliminares de vulnerabilidades, aplicando as correções técnicas no código-fonte e servidor (*patching*). |
| **Semana 8** | **Entrega dos Relatórios e Apresentação** | Envio dos relatórios finais (Red Team com Prova de Conceito; Blue Team com Análise de Logs e Correções). Apresentação dos resultados e conclusões. |

---

## 8. Critérios de Avaliação e Composição da Nota

A nota final do projeto será composta em partes iguais **(50% Defesa / 50% Ataque)**:

### 🔵 Avaliação Blue Team (50% da Nota)

- **Requisitos do Sistema (15%):** Cumprimento das funcionalidades (Login, RBAC, 50 usuários no banco, logs ativos e coerência com o modelo de negócio).
- **Métricas de Defesa e SLA (15%):** Resiliência da aplicação durante os ataques e capacidade de reestabelecer o serviço dentro do tempo limite de SLA (10 minutos de *downtime* tolerado).
- **Análise de Logs e Patching (20%):** Relatório demonstrando a identificação dos ataques via logs e a aplicação de correções eficazes no código-fonte.

### 🔴 Avaliação Red Team (50% da Nota)

- **Mapeamento e Reconhecimento (10%):** Qualidade da fase inicial de varredura, enumeração de portas e identificação da superfície de ataque.
- **Execução dos Ataques e Phishing (15%):** Construção da engenharia social direcionada ao auditor e exploração prática das falhas encontradas no sistema rival.
- **Relatório de Penetration Testing com PoC (25%):** Documento técnico com a Prova de Conceito (*Proof of Concept*) demonstrando o passo a passo para reprodução das falhas, *payloads* utilizados, impacto gerado e orientações de correção.
