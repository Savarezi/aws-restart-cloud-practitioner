# 🧪 Labs/Lab EC2 Auto Scaling


<img width="480" height="360" alt="image" src="https://github.com/user-attachments/assets/ad27ac1c-3b37-4c0b-a811-281477f3e721" />

##


## 🎯 Objetivo

Este laboratório teve como objetivo principal configurar uma **arquitetura elástica e de alta disponibilidade** na AWS, utilizando o **Amazon EC2 Auto Scaling** e um **Elastic Load Balancer (ELB)**.

O processo envolveu a criação de uma **Amazon Machine Image (AMI)** personalizada a partir de uma instância base e o uso dessa AMI para provisionar um grupo de servidores web que se ajusta dinamicamente à carga de tráfego.

## 🪜 Passos

As principais etapas do laboratório e os serviços utilizados foram:

### 1. Preparação da Imagem (AMI) com AWS CLI

* **Conexão e Configuração da AWS CLI:** Acessada a instância `Command Host` e configurada a AWS CLI (região, formato `json`).
* **Criação da Instância Base (`WebServer`):**
    * Utilizado o comando `aws ec2 run-instances` com um script `UserData.txt` para instalar e configurar um servidor web PHP (simulador de stress).
    * Monitorado o status da instância (`aws ec2 wait instance-running`).
    * Teste do servidor web via DNS Público.
* **Criação da AMI Personalizada:**
    * Criada a imagem a partir da instância em execução: `aws ec2 create-image --name WebServerAMI --instance-id NEW-INSTANCE-ID`.

### 2. Configuração do Ambiente de Auto Scaling

* **Criação do Application Load Balancer (ALB):**
    * Nome: `WebServerELB`.
    * Mapeamento em `Sub-rede pública 1` e `Sub-rede pública 2` (alta disponibilidade).
    * Uso do Grupo de Segurança `HTTPAccess`.
* **Criação do Grupo de Destino (Target Group):**
    * Nome: `webserver-app`.
    * Verificação de integridade (Health Check) em `/index.php`.
    * Associado ao ALB.
* **Criação do Modelo de Execução (Launch Template):**
    * Nome: `web-app-launch-template`.
    * Configurado para usar a **`WebServerAMI`** e o tipo de instância `t3.micro`.
    * Associado ao Grupo de Segurança `HTTPAccess`.
* **Criação do Grupo do Auto Scaling (ASG):**
    * Nome: `Web App Auto Scaling Group`.
    * Utilizado o `web-app-launch-template`.
    * **Sub-redes:** `Sub-rede privada 1` e `Sub-rede privada 2`.
    * **Capacidade:** Mínima: 2 | Desejada: 2 | Máxima: 4.
    * **Política de Scaling (Expansão):** Política de rastreamento de destino para manter a **Média de utilização da CPU** em **50%**.
    * Anexado ao ALB e ao Grupo de Destino `webserver-app`.

### 3. Verificação e Teste

* Monitoramento das instâncias iniciadas pelo ASG (Status `2/2 checks passed`).
* Verificação do status dos Alvos no Grupo de Destino (Status `íntegro`).
* **Teste de Estresse:** Acessado o DNS do ALB e clicado em **"Iniciar stress"**.
* Observada a aba **Atividade** do ASG para confirmar a invocação da política de expansão (scale-out) e o lançamento de novas instâncias do EC2 em resposta ao aumento da utilização da CPU (acima de 50%).

## 💡 Resultado

O laboratório resultou em uma arquitetura de aplicação web resiliente e escalável, demonstrando a funcionalidade essencial do Amazon EC2 Auto Scaling e do Elastic Load Balancing.

* **Alta Disponibilidade:** A aplicação é distribuída por múltiplas Zonas de Disponibilidade (Sub-redes Privadas) e o tráfego é roteado pelo ALB (em Sub-redes Públicas).
* **Escalabilidade Automática:** A configuração da política de scaling com rastreamento de métrica (`Média de utilização da CPU <= 50%`) garantiu que o grupo adicionasse automaticamente novas instâncias (de 2 para 3, ou até 4) quando a carga simulada elevou o uso da CPU, provando a capacidade de resposta do sistema a uma carga variável.
* **Automação:** A criação de uma AMI e de um Modelo de Execução padronizou a forma como as novas instâncias são lançadas pelo ASG.

A arquitetura final atingiu o objetivo de ser dimensionada automaticamente sob carga variável, com o tráfego balanceado por meio do ELB.
