# 🧪 Labs/Lab Sandbox

<img width="185" height="185" alt="image" src="https://github.com/user-attachments/assets/79541cea-4117-4472-947e-1696a4fe3d10" />


## 🎯 Objetivo
Criar uma instância EC2 mínima em um ambiente sandbox, acessar via SSH (PuTTY), subir uma página HTML simples (com meu nome) e testar o servidor web. Parar/encerrar a instância após 30 minutos para não consumir recursos desnecessários.

## 🪜 Passos
### 🔧 Provisionamento
- **Serviço usado:** Amazon EC2 (instância Linux)  
- **Tipo de instância:** `t2.micro` (ou `t3.micro` — baixo custo para testes)
- **Par de chaves:** criado arquivo `.pem` e configurado Security Group permitindo:  
  - **SSH (porta 22)** — acesso via PuTTY  
  - **HTTP (porta 80)** — para servir a página

---

### 🚀 Lançamento
- Lancei a instância usando a **AMI Linux (Amazon Linux ou similar)**.  
- Associei a key pair criada no passo anterior.

---

### 💻 Conexão via PuTTY (Windows)
1. Converti o arquivo `.pem` para `.ppk` usando **PuTTYgen**.  
2. No **PuTTY**:
   - **Host:** `ec2-user@<PUBLIC_IP>`  
   - **Auth:** selecionei o arquivo `.ppk`  
3. Conectei com sucesso à instância via SSH.

---

### ⚙️ Operações no Servidor

#### Atualizar pacotes
```bash
# Amazon Linux / RHEL
sudo yum update -y

# Ubuntu / Debian
sudo apt update && sudo apt upgrade -y
```
## Criar arquivo HTML simples

```bash
cat > index.html <<'HTML'
<!doctype html>
<html>
  <head><meta charset="utf-8"><title>Minha página</title></head>
  <body>
    <h1>Paty Oliveira</h1>
    <p>Laboratório: ambiente sandbox — instância EC2</p>
  </body>
</html>
HTML
```
# Servir a página rapidamente (modo teste)

```bash
# Porta 8000 sem sudo
python3 -m http.server 8000

# Ou porta 80 (pode exigir sudo)
sudo python3 -m http.server 80
```
# (Alternativa) Usar Apache

```bash
# Instalar e iniciar Apache (Amazon Linux)
sudo yum install -y httpd
sudo systemctl enable --now httpd

# Mover arquivo HTML para diretório público
sudo mv index.html /var/www/html/index.html
```
⏱ Tempo de Uso

Configurei 30 minutos de execução.

Após os testes, encerrei a instância para evitar custos e liberar recursos.

Encerramento:

Via Console AWS:
Instances → selecionar → Stop ou Terminate

Via CLI (opcional):

aws ec2 stop-instances --instance-ids i-xxxxxxxxx

##
🌐 Observação sobre Acesso

Página acessível em:
http://<PUBLIC_IP>:8000/ (ou :80 se usar Apache)

Se o HTTP não abrir:

Verifique o Security Group (porta 80 aberta para seu IP ou 0.0.0.0/0)

Confirme se o servidor está rodando (python3 -m http.server ou systemctl status httpd)

## 💡 Resultado
Instância EC2 criada e acessada com sucesso via PuTTY.

Página HTML criada e servida corretamente.

Entendimento dos conceitos de key pair, Security Group e tempo de execução.

Prática de boas rotinas de uso: encerrar instâncias após o teste.

Aprendi a diferença entre rodar um servidor simples e usar o Apache.
