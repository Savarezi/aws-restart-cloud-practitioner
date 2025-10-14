# 🧪 Lab IAM – Gerenciamento de Usuários, Grupos e Políticas na AWS

<img width="360" height="180" alt="image" src="https://github.com/user-attachments/assets/bcb12f13-3628-4750-8c41-0ec374220864" />


## 🎯 Objetivo
Explorar o serviço **AWS Identity and Access Management (IAM)** para:
- Criar e aplicar uma política de senhas.
- Inspecionar usuários, grupos e políticas (gerenciadas e inline).
- Atribuir usuários a grupos por função.
- Testar, em prática, o controle de acesso aos serviços **EC2** e **S3**.

---

## 🔗 Link de acesso (IAM sign-in)
**URL de login IAM (para testes):**  



---

## 🪜 Passos realizados

### 1. Política de Senhas (IAM → Account settings)
- Comprimento mínimo: **10 caracteres**  
- Requisitos de complexidade:
  - Pelo menos **uma letra maiúscula (A–Z)**
  - Pelo menos **uma letra minúscula (a–z)**
  - Pelo menos **um número (0–9)**
  - Pelo menos **um caractere não alfanumérico** (ex.: `! @ # $ % ^ & * ( ) _ + - = [ ] { } | '`)
- Expiração de senha: **90 dias**  
- Impedir reutilização: lembrar últimas **5** senhas  
- **Não** marcar: *Password expiration requires administrator reset*  
- Permitir que usuários alterem a própria senha: **sim**

> Resultado: fortalecimento das credenciais de conta, alinhado a boas práticas.

---

### 2. Explorar usuários e grupos (IAM → Users / User groups)
- Usuários criados no lab:
  - `user-1`
  - `user-2`
  - `user-3`
- Grupos existentes:
  - **S3-Support** → `AmazonS3ReadOnlyAccess` (read-only S3)
  - **EC2-Support** → `AmazonEC2ReadOnlyAccess` (read-only EC2)
  - **EC2-Admin** → política **inline** (Describe + Start/Stop instances)

> Observação: políticas gerenciadas aplicam-se a todos os anexados; inline é específica ao grupo.

---

### 3. Adicionar usuários aos grupos
Atribuições aplicadas:

| Usuário  | Grupo        | Permissão esperada                    |
|---------:|--------------|----------------------------------------|
| user-1   | S3-Support   | Leitura (S3)                           |
| user-2   | EC2-Support  | Leitura (EC2)                          |
| user-3   | EC2-Admin    | Start / Stop + Describe (EC2)          |

**Como feito (Console):**
- IAM → **User groups** → selecionar grupo → aba **Users** → **Add users** → marcar usuário → **Add users**

**Via AWS CLI (opcional):**
```bash
aws iam add-user-to-group --group-name S3-Support --user-name user-1
aws iam add-user-to-group --group-name EC2-Support --user-name user-2
aws iam add-user-to-group --group-name EC2-Admin --user-name user-3
```
## 🧩 4. Testes práticos (janela privada / incognito)

**Teste realizado para cada usuário com as credenciais do lab:**

### 👤 user-1 (`Lab-Password1`)
- **Acessou S3:** ✅ Sim (listar e visualizar buckets)  
- **Acessou EC2:** ❌ Não — mensagem *"You are not authorized"*

### 👤 user-2 (`Lab-Password2`)
- **Acessou EC2:** ✅ Sim (visualizar instâncias)  
- **Tentou Stop instance:** ❌ Falha — *somente leitura*  
- **Acessou S3:** ❌ Não

### 👤 user-3 (`Lab-Password3`)
- **Acessou EC2:** ✅ Sim  
- **Parou/Iniciou instância:** ✅ Sucesso — *Start/Stop permitido*

> 💡 **Dica:** Se nenhuma instância aparecer no EC2, confira a região no canto superior direito (ex.: `us-east-1` vs `us-east-2`).

---

## 💡 Observações & Aprendizado

- 🔒 **Princípio do Least Privilege** validado: cada usuário obteve apenas o necessário.  
- 👥 **Grupos IAM** são a forma mais eficiente de aplicar permissões em larga escala.  
- 🧱 **Política de senha** aplicada garante maior resistência a ataques de força bruta.  
- ⚠️ Mensagem *"not authorized"* em `CloudWatch/alarms` é normal quando o usuário não tem permissão `cloudwatch:DescribeAlarms`.

---

## ✅ Checklist Final

- [x] Política de senha aplicada (mín. 10 caracteres, complexidade, expiração 90d, reuso 5)  
- [x] `user-1` adicionado ao grupo **S3-Support**  
- [x] `user-2` adicionado ao grupo **EC2-Support**  
- [x] `user-3` adicionado ao grupo **EC2-Admin**  
- [x] Testes de login e validação de permissões realizados com sucesso
