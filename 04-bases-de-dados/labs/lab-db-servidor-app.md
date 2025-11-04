# 🧪 Criar um Servidor de Banco de Dados e Interagir com o Aplicativo

Este documento registra a execução do laboratório prático focado na implantação e interação com o **Amazon Relational Database Service (Amazon RDS)**.

## 🎯 Objetivo

O principal objetivo deste laboratório foi reforçar o conceito de utilização de um serviço de banco de dados relacional gerenciado pela AWS (Amazon RDS) e integrá-lo a um aplicativo web para persistência de dados.

**Ao final do laboratório, fomos capazes de:**

* **Executar** uma instância de banco de dados do Amazon RDS em arquitetura **Multi-AZ** (Alta Disponibilidade).
* **Configurar** o acesso à instância de banco de dados, permitindo conexões seguras a partir de um servidor web (EC2).
* **Abrir e interagir** com um aplicativo web, comprovando a utilização do banco de dados provisionado.

## 🪜 Passos

As seguintes tarefas foram executadas no Console de Gerenciamento da AWS para configurar a infraestrutura e o banco de dados:

### Tarefa 1: Criar um Grupo de Segurança para o RDS

1.  Criação do Grupo de Segurança (SG) `DB Security Group` na **VPC do Laboratório**.
2.  Adição de uma **Regra de Entrada** permitindo tráfego na porta **3306 (MySQL/Aurora)**, com a **Origem** definida para o `Web Security Group` existente.

### Tarefa 2: Criar um Grupo de Sub-redes de Banco de Dados

1.  Criação do `DB Subnet Group` na VPC do laboratório.
2.  Associação das sub-redes privadas de **duas Zonas de Disponibilidade distintas** (Sub-rede 1: `10.0.1.0/24` e Sub-rede 2: `10.0.3.0/24`) para garantir a arquitetura Multi-AZ.

### Tarefa 3: Criar uma Instância de Banco de Dados do Amazon RDS

1.  Configuração de uma nova instância de banco de dados:
    * **Tipo de Mecanismo:** MySQL (versão mais recente).
    * **Modelo:** Dev/teste.
    * **Disponibilidade e Durabilidade:** Instância de banco de dados **Multi-AZ** (para alta disponibilidade).
    * **Identificador:** `lab-db`.
    * **Usuário/Senha:** `main` / `lab-password`.
    * **Classe:** `db.t3.medium` (Classes com capacidade de intermitência).
    * **Segurança:** Associada ao `DB Security Group` criado na Tarefa 1.
    * **Configuração Adicional:** Nome do banco de dados inicial: `lab`.
2.  Aguardar o status da instância mudar para **Disponível**.
3.  Cópia do **Endpoint** da instância para uso na próxima tarefa.

### Tarefa 4: Interagir com o Banco de Dados

1.  Acesso ao aplicativo web via endereço **IP do WebServer**.
2.  Navegação até o link **RDS** do aplicativo.
3.  Configuração da conexão do aplicativo:
    * **Endpoint:** Endpoint copiado do RDS.
    * **Banco de Dados:** `lab`.
    * **Nome do Usuário:** `main`.
    * **Senha:** `lab-password`.
4.  Submissão das credenciais, permitindo que o aplicativo estabelecesse a conexão e criasse o `Address Book`.

## 💡 Resultado

O laboratório resultou na implantação bem-sucedida de um ambiente de banco de dados resiliente e seguro:

* **Conectividade Estabelecida:** O `DB Security Group` garantiu que apenas o servidor web (via `Web Security Group`) pudesse se conectar ao RDS.
* **Alta Disponibilidade (Multi-AZ):** A instância do RDS foi configurada para ter uma réplica de espera sincronicamente em uma Zona de Disponibilidade diferente, garantindo durabilidade e failover automático em caso de falha da AZ primária.
* **Persistência de Dados:** Foi possível interagir com o aplicativo `Address Book` (adicionar, editar, remover contatos), comprovando que os dados estavam sendo armazenados e replicados com sucesso no banco de dados do Amazon RDS.

<img width="1064" height="507" alt="image" src="https://github.com/user-attachments/assets/17708505-f3a3-4fc8-a69b-0f6f39031622" />
