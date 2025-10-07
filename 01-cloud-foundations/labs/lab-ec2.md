# 🧪 Labs/Lab Ec2


<img width="320" height="180" alt="image" src="https://github.com/user-attachments/assets/0fd94fac-24eb-4276-9d46-5925066adf46" />



## 🎯 Objetivo
Este laboratório apresenta uma visão geral básica de como executar, redimensionar, gerenciar e monitorar uma instância do Amazon EC2.

O Amazon Elastic Compute Cloud (Amazon EC2) é um serviço da web que fornece capacidade computacional redimensionável na nuvem. Ele foi projetado para facilitar a computação em nuvem na escala da web para os desenvolvedores.

A interface de serviço da web simples do Amazon EC2 permite que você obtenha e configure capacidade com o mínimo de esforço. Ela oferece um controle completo de seus recursos de computação e permite a execução no ambiente de computação comprovado da Amazon. O Amazon EC2 reduz o tempo necessário para obter e inicializar novas instâncias do servidor em minutos, permitindo o rápido escalonamento da capacidade para mais ou para menos, de acordo com a evolução dos requisitos de computação.

O Amazon EC2 altera a economia da computação, permitindo que você pague somente pela capacidade que realmente utiliza. O Amazon EC2 oferece aos desenvolvedores as ferramentas para criar aplicações resistentes a falhas e isolá-los de situações de falha comuns.

Tópicos abordados
Ao final deste laboratório, você será capaz de:

1- Iniciar um servidor web com proteção contra encerramento ativada

2- Monitorar sua instância do EC2

3- Modificar o grupo de segurança que seu servidor web está usando para permitir acesso HTTP

4- Redimensionar sua instância do Amazon EC2 de acordo com a necessidade

5- Testar a proteção contra encerramento

# Terminar a instância do EC2

## 🪜 Passos
# Laboratório Amazon EC2

Este guia descreve como iniciar, monitorar, acessar e redimensionar uma instância do Amazon EC2, incluindo proteção contra encerramento e configuração de um servidor web simples.

---

## Tarefa 1: Iniciar sua instância do EC2

A proteção contra encerramento impede que você encerre acidentalmente uma instância do EC2. Nesta tarefa, você também implantará um servidor web simples usando um script de dados do usuário.

### Passos:

1. No **Console de Gerenciamento da AWS**, vá em **Serviços > EC2**.
2. No painel de navegação à esquerda, clique em **Painel do EC2**.
3. Clique em **Executar instância**.

### Etapa 1: Nomear sua instância
- No painel **Name and tags**, digite o nome: `Web Server`.

### Etapa 2: Selecionar uma AMI
- Use a **Amazon Linux 2023** (padrão).

### Etapa 3: Selecionar um tipo de instância
- Escolha **t3.micro** (2 vCPUs, 1 GiB memória).

### Etapa 4: Configurar um par de chaves
- Selecione **Proceed without a key pair** (Prosseguir sem um par de chaves).

### Etapa 5: Configurar rede
- VPC: **Lab VPC**
- Grupo de segurança:
  - Nome: `Web Server security group`
  - Descrição: `Security group for my web server`
  - Remova regras existentes
- **Observação:** SSH não será usado neste laboratório.

### Etapa 6: Adicionar armazenamento
- Mantenha o volume padrão: 8 GiB.

### Etapa 7: Configurar detalhes avançados
- Ative **Termination protection** (Proteção contra encerramento).
- Adicione o seguinte **User data**:

```bash
#!/bin/bash
yum -y install httpd
systemctl enable httpd
systemctl start httpd
echo '<html><h1>Hello From Your Web Server!</h1></html>' > /var/www/html/index.html 
```
## Iniciar e Monitorar a Instância

- Clique em **Executar instância** e aguarde até ficar **Em execução**.
- Verifique as guias **Details**, **Security** e **Networking**.
- Em **Status checks**, confirme **System reachability** e **Instance reachability** (2/2 aprovadas).
- Use **Get Instance Screenshot** se quiser visualizar a instância.

---

## Acessar o Servidor Web

1. Copie o **Public IPv4 address** e abra no navegador.
   - Ainda não acessa: tráfego HTTP bloqueado.
2. Corrija no grupo de segurança:
   - Vá em **Security Groups > Web Server security group > Inbound rules > Editar**.
   - Adicione: **Tipo: HTTP**, **Origem: IPv4 em qualquer lugar**.
   - Salve e atualize a página.
3. Você verá: `Hello From Your Web Server!`

---

## Redimensionar a Instância

1. **Interromper:** Estado da instância > Interromper instância → aguarde **Stopped**.
2. **Alterar tipo:** Configurações de instância > Alterar tipo → **t3.small**.
3. **Redimensionar volume:** Volumes > Selecionar volume > Modificar → tamanho 10 GiB → confirmar.
4. **Iniciar:** Selecione a instância > Iniciar instâncias.

---

## Testar Proteção contra Encerramento

1. Tente **Encerrar instância** → não funcionará.
2. Vá em **Configurações de instância > Change termination protection** → desmarque **Enable** e salve.
3. Agora finalize a instância normalmente.


## 💡 Resultado
Durante o laboratório, observei como iniciar e configurar uma instância EC2, incluindo escolha de AMI, tipo de instância, rede, segurança e armazenamento. Aprendi a usar o User Data para instalar automaticamente um servidor web e criar uma página simples, além de entender a importância dos grupos de segurança, que controlam o tráfego de entrada e saída. Testei a proteção contra encerramento, confirmei o monitoramento da instância via Status Checks e CloudWatch, e pratiquei o redimensionamento da instância e do volume EBS. O laboratório reforçou conceitos de automação, segurança, monitoramento e flexibilidade de gerenciamento de instâncias na nuvem.
