# 📘 02 Redes

# 🌐 Laboratório: Criação de VPC e Servidor Web na AWS

<img width="160" height="106" alt="image" src="https://github.com/user-attachments/assets/3c6ae7cf-1a9f-4ffa-9511-e5df62fb0698" />


## 📖 Descrição
Neste laboratório, foi utilizada a **Amazon Virtual Private Cloud (VPC)** para criar uma rede personalizada para um cliente Fortune 100.  
O objetivo foi montar uma infraestrutura completa, com **VPC, sub-redes públicas e privadas, gateway da Internet, gateway NAT** e **uma instância EC2 configurada como servidor web**.

---

## 🧠 Objetivos Principais
- Criar e configurar uma **VPC personalizada**
- Adicionar **sub-redes públicas e privadas**
- Configurar **tabelas de rotas**
- Criar e associar **grupos de segurança**
- Executar uma **instância EC2** e transformá-la em um **servidor web**

---

## 🧩 Etapas Realizadas

### 🏗️ Tarefa 1: Criação da VPC
Utilizando o **Assistente de VPC**, foram configuradas as seguintes opções:

| Configuração | Valor |
|---------------|--------|
| IPv4 CIDR | `10.0.0.0/16` |
| IPv6 CIDR | Nenhum |
| Tenancy | Padrão |
| Nº de Zonas de Disponibilidade | 1 |
| Sub-redes públicas | 1 |
| Sub-redes privadas | 1 |
| Gateway NAT | Em 1 AZ |
| Endpoints da VPC | Nenhum |

**Recursos nomeados:**
- **VPC:** `Lab VPC`
- **Sub-redes:** `Public Subnet 1` e `Private Subnet 1`
- **Tabelas de rota:** `Public Route Table` e `Private Route Table`

📊 **Diagrama da VPC Inicial:**  
 <img width="1114" height="511" alt="image" src="https://github.com/user-attachments/assets/c7112e1f-1e03-4f2e-ab1a-41310cbb1673" />


---

### 🌍 Tarefa 2: Criação de Sub-redes Adicionais
Duas novas sub-redes foram criadas para garantir **alta disponibilidade**, em uma segunda Zona de Disponibilidade.

| Sub-rede | Tipo | Bloco CIDR |
|-----------|------|-------------|
| Public Subnet 2 | Pública | `10.0.2.0/24` |
| Private Subnet 2 | Privada | `10.0.3.0/24` |

📊 **Diagrama da VPC Expandida:**  
 <img width="1106" height="510" alt="image" src="https://github.com/user-attachments/assets/3ed18b1c-d245-4681-85b0-0e976878b367" />


---

### 🧭 Tarefa 3: Associação das Sub-redes e Rotas
As novas sub-redes foram associadas às tabelas de rota correspondentes:

- **Public Route Table →** Public Subnet 1 e Public Subnet 2  
- **Private Route Table →** Private Subnet 1 e Private Subnet 2  

Após isso, a VPC passou a possuir sub-redes públicas e privadas em **duas Zonas de Disponibilidade**.

---

### 💻 Tarefa 4: Criação do Servidor Web (EC2)
Foi iniciada uma **instância EC2** configurada como servidor web:

| Configuração | Valor |
|---------------|--------|
| Nome | `Web Server 1` |
| AMI | `Amazon Linux 2 (HVM)` |
| Tipo de instância | `t3.micro` |
| Par de chaves | `vockey` |
| VPC | `Lab VPC` |
| Sub-rede | Pública |
| IP público | Habilitado |
| Grupo de segurança | `Web Security Group` |

#### 🔧 Script de inicialização (User Data)

```bash
#!/bin/bash
yum update -y
yum install -y httpd
systemctl start httpd
systemctl enable httpd
echo '<!DOCTYPE html>
<html lang="pt-br">
<head>
<meta charset="UTF-8">
<title>Olá Mundo</title>
<style>
  body {
    margin: 0;
    height: 100vh;
    background: linear-gradient(135deg, #6a0dad, #8a2be2, #9370db);
    color: white;
    font-family: "Segoe UI", sans-serif;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
  }
  h1 {
    font-size: 3em;
    background: rgba(0,0,0,0.3);
    padding: 20px 40px;
    border-radius: 15px;
    box-shadow: 0 0 20px rgba(0,0,0,0.5);
    animation: glow 2s infinite alternate;
  }
  @keyframes glow {
    from { text-shadow: 0 0 10px #fff; }
    to { text-shadow: 0 0 25px #fff, 0 0 50px #d8b9ff; }
  }
</style>
</head>
<body>
  <h1>OLA MUNDO DE '$(hostname -f)'</h1>
</body>
</html>' > /var/www/html/index.html

```

🧱 Arquitetura Final Implantada

A infraestrutura resultante incluiu:

1 VPC principal (10.0.0.0/16)

4 sub-redes (2 públicas e 2 privadas)

1 Gateway da Internet

1 Gateway NAT

Tabelas de rota públicas e privadas

1 instância EC2 rodando servidor Apache

📊 Diagrama da Arquitetura Final:
<img width="1114" height="511" alt="image" src="https://github.com/user-attachments/assets/05573f9c-e6ad-487d-b0f4-8f9cc38b163e" />

##
📝 Notas Pessoais

O uso do assistente de VPC facilita bastante a criação inicial, mas entender cada componente é essencial.

As tabelas de rotas são a espinha dorsal da comunicação entre sub-redes e Internet.

O gateway NAT foi fundamental para permitir que as instâncias privadas acessassem a Internet sem ficarem expostas.

A configuração do script no User Data automatizou totalmente o setup do servidor web, economizando tempo.

##
💡 Resultado Final:
Ambiente funcional de rede na AWS, com VPC configurada, sub-redes, gateways, rotas e instância EC2 operacional exibindo a página “Olá Mundo”.


