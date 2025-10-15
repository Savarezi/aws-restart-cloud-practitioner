# 🧪 Labs/Lab Rds

# Amazon RDS com EC2


<img width="344" height="180" alt="image" src="https://github.com/user-attachments/assets/c26e67c2-cc87-4723-8086-5f1d466f37b3" />



## 📘 Descrição
Este laboratório tem como objetivo configurar um ambiente completo na AWS integrando uma instância **EC2 (servidor web)** com um **banco de dados MySQL no Amazon RDS**, simulando uma arquitetura multi-AZ com alta disponibilidade.

---

## ⚙️ Estrutura do Laboratório

### **Tarefa 1 – Criar o Grupo de Segurança do Banco de Dados**
- **Nome:** `DB Security Group`  
- **Descrição:** Permit access from Web Security Group  
- **VPC:** `Lab VPC`  
- **Regra de entrada:**  
  - **Tipo:** MySQL/Aurora (porta 3306)  
  - **Origem:** `Web Security Group`  

👉 Isso permite que o servidor web (EC2) acesse o banco de dados.

---

### **Tarefa 2 – Criar Grupo de Sub-redes do RDS**
- **Nome:** `DB Subnet Group`  
- **Descrição:** DB Subnet Group  
- **VPC:** `Lab VPC`  
- **Sub-redes:**  
  - 10.0.1.0/24 (AZ1)  
  - 10.0.3.0/24 (AZ2)

💡 Esse grupo define onde o RDS pode criar instâncias (duas Zonas de Disponibilidade diferentes).

---

### **Tarefa 3 – Criar Instância do Banco de Dados (RDS)**
- **Tipo de banco:** MySQL  
- **Versão:** mais recente disponível  
- **Modelo:** Dev/Teste  
- **Disponibilidade:** Multi-AZ  
- **Identificador:** `lab-db`  
- **Usuário principal:** `main`  
- **Senha:** `lab-password`  
- **Classe:** `db.t3.medium`  
- **Tipo de armazenamento:** SSD (General Purpose)  
- **VPC:** Lab VPC  
- **Grupo de segurança:** `DB Security Group`  
- **Banco inicial:** `lab`  
- **Backups automatizados:** desativados  

📍 Ao final, o **endpoint** foi copiado para conectar o aplicativo web.

---

### **Tarefa 4 – Conectar o Aplicativo Web ao RDS**
- Abra o IP público do servidor EC2 no navegador.  
- Clique na aba **RDS** do aplicativo.  
- Preencha as credenciais:  
  - **Endpoint:** (copiado do RDS)  
  - **Database:** `lab`  
  - **Usuário:** `main`  
  - **Senha:** `lab-password`  

✅ Após enviar, o aplicativo exibiu o **Address Book**, usando o banco do RDS para armazenar os dados.

---

## 🧩 Resultado
O aplicativo web foi integrado com sucesso ao banco de dados MySQL no RDS, com replicação automática entre zonas de disponibilidade.  
As operações de **inserção, edição e exclusão de contatos** foram persistidas corretamente.

---

## 🏁 Conclusão
Laboratório concluído com sucesso!  
A arquitetura final demonstrou:
- Comunicação segura entre EC2 e RDS.  
- Alta disponibilidade via Multi-AZ.  
- Uso de grupos de segurança e sub-redes bem configurados.

---

**© AWS Training & Certification**  
Material adaptado para fins educacionais.
