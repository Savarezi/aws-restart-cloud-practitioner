# 🧪 Labs/Lab Cloudtrail
<img width="318" height="159" alt="image" src="https://github.com/user-attachments/assets/e9fec001-de4e-47d5-b5fe-fd32398269c6" />


## Investigação de Violação de Segurança com AWS CloudTrail e Athena 🛡️

<img width="814" height="437" alt="image" src="https://github.com/user-attachments/assets/8574ad71-17ee-4a90-a356-2b839975f917" />


---

### 🎯 Objetivo

O principal objetivo deste laboratório foi **investigar uma violação de segurança** no site da Cafeteria Café hospedado em uma instância **Amazon EC2** Linux. 

<img width="227" height="177" alt="image" src="https://github.com/user-attachments/assets/d3a53612-56f2-45d4-ab49-0a6dab3bc6c6" />

## A atividade focou em:

1.  Configurar uma trilha do **AWS CloudTrail** para auditar as ações da conta.
2.  Analisar os logs do CloudTrail usando **`grep`**, **AWS CLI** e **Amazon Athena** para identificar o usuário responsável por modificar as regras do Grupo de Segurança (SG).
3.  **Remover o acesso do invasor** e **reforçar as defesas de segurança** da conta AWS e do servidor web.

---

### 🪜 Passos Executados

As seguintes tarefas e etapas foram executadas no ambiente AWS:

#### 1. Criação da Trilha e Detecção da Violação
* Criada a trilha **CloudTrail** (`monitor`) com logs armazenados no **Amazon S3** (`monitoring####`).
* Confirmado que, após a criação da trilha, o site foi **violado** (imagem inapropriada) e o SG do servidor web foi modificado para permitir acesso **SSH de qualquer lugar** (`0.0.0.0/0`).

#### 2. Análise de Logs (SSH, CLI e Athena)
* Conexão via **SSH** à instância `Cafe Web Server` e download/extração dos logs do CloudTrail.
* Análise inicial usando **`grep`** e o comando **AWS CLI `aws cloudtrail lookup-events`** para filtrar eventos relacionados a `SecurityGroup`.
* Criação de uma tabela externa no **Amazon Athena** (`cloudtrail_logs_monitoring####`) sobre os logs do CloudTrail.
* Execução de consultas **SQL** no Athena para identificar o evento exato de violação:

    ```sql
    -- Consulta para identificar quem abriu o SSH para o mundo
    SELECT 
        useridentity.userName, 
        eventtime, 
        requestparameters 
    FROM 
        cloudtrail_logs_monitoring#### 
    WHERE 
        eventName = 'AuthorizeSecurityGroupIngress' 
        AND requestparameters LIKE '%0.0.0.0/0%'
    ```

#### 3. Identificação e Remediação de Segurança
* **Hacker Identificado:** O usuário AWS **Faythe** executou a ação maliciosa.
* **Remoção do Invasor:**
    * Identificação do usuário do SO invasor, **`chaos-user`**, usando `sudo aureport --auth` e `who`.
    * Encerramento da sessão e exclusão do usuário do SO: `sudo kill -9 ProcNum` seguido por `sudo userdel -r chaos-user`.
* **Reforço do SSH:**
    * Edição do `/etc/ssh/sshd_config` para desativar a autenticação por senha (`#PasswordAuthentication yes` e `PasswordAuthentication no`).
    * Reinicialização do serviço SSH: `sudo service sshd restart`.
* **Correção do Grupo de Segurança:** Remoção da regra de entrada do SG que permitia **SSH de `0.0.0.0/0`**.

---

### 💡 Resultado

A investigação foi concluída com sucesso, resultando na **identificação do usuário AWS Faythe** como o responsável pela modificação do SG e subsequente invasão do servidor (provavelmente explorando a `PasswordAuthentication` habilitada no sistema operacional).

As principais medidas de segurança tomadas foram:

* **Responsável:** Usuário AWS **Faythe**.
* **Ação:** **`AuthorizeSecurityGroupIngress`** (Adicionar regra SSH 0.0.0.0/0).
* **Prevenção:** **Desativação da autenticação por senha** no SSH, remoção da regra de SG vulnerável e exclusão do usuário invasor do SO.
