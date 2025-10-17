# 🧪 Lab CLI

<img width="344" height="180" alt="image" src="https://github.com/user-attachments/assets/251562df-04c3-40a2-9aa9-b137856ebbbc" />



## 🎯 Objetivo
Aprender a instalar, configurar e utilizar a **AWS CLI** em uma instância Linux do Red Hat, conectando-a a uma conta da AWS para gerenciar recursos como EC2, S3 e IAM via linha de comando.

---

## 🪜 Passos

1. **Conectar-se à instância EC2 via SSH**
   ```bash
   ssh -i labsuser.ppk ec2-user@34.216.76.12   ```
   

  
##
2. **Instalar a AWS CLI**

* curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
* unzip -u awscliv2.zip
* sudo ./aws/install
* aws --version

##

3. **Configurar a AWS CLI com credenciais do usuário de laboratório**
aws configure

 * Access Key ID:*******************

 * Secret Access Key: ****************************
 * Default region: us-west-2
 
 * Output format: json

##

4. **Testar a configuração da CLI**

* aws s3 ls
  aws iam list-users

##

5. **Desafio: baixar o documento lab_policy em JSON**


* aws iam list-policies --scope Local

* aws iam get-policy-version --policy-arn <ARN_da_lab_policy> --version-id v1 > lab_policy.json


##
💡 Resultado

*  A AWS CLI foi instalada e configurada corretamente na instância Linux.

*  Foi possível listar usuários e políticas do IAM, interagir com S3 e verificar a comunicação entre CLI e conta AWS.

*  O documento lab_policy.json foi baixado, mostrando a política do usuário do lab em formato JSON.

*  Aprendi a gerenciar recursos da AWS de forma programática, usando linha de comando, sem depender do console gráfico, o que agiliza operações e permite automação.







