

## 📝 Detalhamento do Laboratório: `lab-cloudformation.md`

### 🏗️ Laboratório: Automação com o CloudFormation

Este laboratório interativo fornece experiência prática na implantação, edição e gerenciamento do ciclo de vida de **AWS CloudFormation Stacks**. O foco principal é demonstrar como o IaC garante consistência, confiabilidade e automação na criação de infraestrutura, eliminando a necessidade de procedimentos manuais sujeitos a erros.

**Objetivos de Aprendizagem:**

O laboratório demonstrou como utilizar o CloudFormation para a automação completa da infraestrutura:

* **Implantação Inicial de Pilha:** Criação de uma nuvem privada virtual (VPC) e um grupo de segurança (Security Group) a partir de um template YAML.
* **Edição e Atualização de Pilha:** Modificação de um template existente para adicionar um recurso **Amazon S3 Bucket** e a execução de uma atualização de pilha (`UPDATE_IN_PROGRESS`), demonstrando a eficiência da adição de recursos sem a necessidade de reimplantar a infraestrutura existente.
* **Implantação de Recursos Complexos:** Adição de uma instância **Amazon EC2** ao template, utilizando:
    * **AWS Systems Manager Parameter Store** (`AWS::SSM::Parameter::Value`) para recuperar a AMI mais recente de forma dinâmica.
    * **Função `!Ref`** para referenciar outros recursos e parâmetros (Security Group e Subnet) dentro do mesmo template.

#### 💡 Exemplo de Template CloudFormation Corrigido

Para garantir a sintaxe correta do YAML (principalmente a indentação para listas como `SecurityGroupIds`), o template foi revisado e corrigido.


* **Gerenciamento do Ciclo de Vida:** Exclusão completa da pilha, garantindo que todos os recursos provisionados (VPC, IGW, Subnet, EC2, S3, etc.) sejam automaticamente encerrados e removidos da conta AWS.
* 
<img width="1510" height="2002" alt="code" src="https://github.com/user-attachments/assets/2d5b9e5e-3bd6-4b4f-85d4-f0fee9fffd9b" />

**Serviços e Conceitos Chave Explorados:**

* **CloudFormation Stacks, Templates, Parameters, Resources e Outputs.**
* **Sintaxe YAML:** Importância da indentação correta.
* **Funções Intrínsecas:** `!Ref`.
* **Padrões de Referência:** Uso do Parameter Store para *lookup* dinâmico de AMIs.
* **Recursos AWS:** `AWS::EC2::VPC`, `AWS::EC2::SecurityGroup`, `AWS::EC2::Instance`, `AWS::S3::Bucket`, etc.

---

## Pré-requisitos Gerais

Para executar os labs, é altamente recomendado que você tenha:

* Uma **Conta AWS Ativa** (e permissões de IAM adequadas).
* **Conhecimento intermediário** em arquitetura AWS.

---

## 🤝 Como Contribuir

Sinta-se à vontade para abrir *issues* com sugestões de melhoria ou *Pull Requests* se desejar corrigir ou aprimorar algum passo dos laboratórios.
