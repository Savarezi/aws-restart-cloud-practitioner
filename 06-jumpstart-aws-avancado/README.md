# ☁️ Jumpstart AWS Avançado
<img width="292" height="173" alt="image" src="https://github.com/user-attachments/assets/1a088978-71b0-4f49-b2b6-8566ab598413" />
##

Este repositório contém uma série de **laboratórios práticos** (labs) focados em serviços avançados da Amazon Web Services (AWS), essenciais para profissionais que buscam aprofundar seus conhecimentos em **Infraestrutura como Código (IaC)**, **Governança**, **Segurança** e **Observabilidade (Monitoramento)**.

O objetivo é fornecer um *jumpstart* rápido e direto para a configuração e o gerenciamento de recursos críticos de maneira escalável, auditável e proativa.

---

## 🛠️ Laboratórios Incluídos

Os laboratórios estão organizados em arquivos Markdown (`.md`) e cobrem os seguintes serviços principais:

### 1. **[lab-cloudformation.md](lab-cloudformation.md)**
> **Foco: Infraestrutura como Código (IaC)**
>
> Este laboratório guia você na utilização do **AWS CloudFormation**, o serviço nativo da AWS para provisionamento de recursos através de *templates* (modelos declarativos em JSON ou YAML).
>
> **Tópicos Abordados:**
> * Criação e gerenciamento de *Stacks* (Pilhas).
> * Definição de recursos, parâmetros e *Outputs*.
> * Atualizações, *Drift Detection* e gerenciamento de dependências.

### 2. **[lab-cloudtrail.md](lab-cloudtrail.md)**
> **Foco: Governança, Rastreamento e Auditoria**
>
> Este laboratório foca no **AWS CloudTrail**, o serviço que rastreia a atividade da API da AWS, sendo crucial para a segurança, conformidade e auditoria de sua conta.
>
> **Tópicos Abordados:**
> * Configuração de *Trails* (Trilhas) e *Data Event Logging*.
> * Análise de logs no S3 e utilização do CloudTrail Lake (se aplicável).
> * Monitoramento de atividades de usuário e ações de API.

### 3. **[lab-cloudwatch.md](lab-cloudwatch.md)**
> **Foco: Observabilidade e Monitoramento Proativo**
>
> Este laboratório explora o **Amazon CloudWatch**, a ferramenta central de monitoramento e observabilidade da AWS. O foco é ir além das métricas básicas para criar um sistema de alerta e análise eficiente.
>
> **Tópicos Abordados (Avançados):**
> * Criação de **Métricas Personalizadas** (`Custom Metrics`).
> * Configuração de **Alarmes Avançados** (ex: baseados em expressões matemáticas ou Anomalia Detection).
> * Utilização do **CloudWatch Logs Insights** para consultas complexas em logs.
> * Criação de Painéis (*Dashboards*) para uma visão operacional unificada.

---

## Pré-requisitos

Para executar os labs, é altamente recomendado que você tenha:

* Uma **Conta AWS Ativa** (e permissões de IAM adequadas).
* **Conhecimento básico** de serviços AWS, como EC2, S3 e IAM.
* **AWS CLI** configurada localmente (opcional, mas recomendado para automação).

---

## 🤝 Como Contribuir

Sinta-se à vontade para abrir *issues* com sugestões de melhoria ou *Pull Requests* se desejar corrigir ou aprimorar algum passo dos laboratórios!
