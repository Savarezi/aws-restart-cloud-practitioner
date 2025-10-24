

# 🌐 Laboratório AWS S3 – Hospedagem de Site Estático


<img width="951" height="354" alt="image" src="https://github.com/user-attachments/assets/010c464b-3acd-41c4-b545-e84651b9a1d7" />


## 🎯 Objetivo
Configurar um bucket S3 na AWS para hospedar um site estático, automatizando o envio de arquivos através de um script em shell.  
Durante o laboratório, foram utilizados serviços como **EC2**, **S3**, **IAM** e **AWS CLI** para criar, configurar e publicar uma página web simples.

---

## 🪜 Passos

### 🔧 1. Preparação do ambiente
- Acesso à instância **EC2** via **Session Manager (SSM)**.  
- Troca para o usuário padrão:
  ```bash
  sudo su -l ec2-user

``
* Verificação do diretório inicial:
  ```
   pwd
``
##
🧱 2. Criação do bucket no S3

* Criação de um bucket público para hospedar o site.

* Configuração para não bloquear acesso público e habilitar ACLs.

* Nome do bucket: seu-bucket-nome-aqui

🧍‍♀️ 3. Criação de usuário IAM

* Criação do usuário awsS3user com acesso programático.

* Concessão da política AmazonS3FullAccess.

* Login no console com o usuário IAM para testar permissões no S3.
##
💾 4. Extração dos arquivos do site

* No terminal EC2:
```bash

 cd ~/sysops-activity-files

 tar xvzf static-website-v2.tar.gz

 cd static-website

 ls
```
* Verificados os arquivos:

```bash

index.html
css/
images/
```
##
☁️ 5. Upload e configuração do site estático

Configuração do bucket como site:

```bash
 aws s3 website s3://seu-bucket-nome-aqui/ --index-document index.html
```
* Upload dos arquivos:
```bash
 aws s3 cp /home/ec2-user/sysops-activity-files/static-website/ s3://seu-bucket-nome-aqui/ --recursive --acl public-read
```
* Verificação:
 ```bash
 aws s3 ls s3://seu-bucket-nome-aqui
```
##
⚙️ 6. Criação do script de atualização (update-website.sh)

* No diretório home:
```bash
 cd ~
touch update-website.sh
vi update-website.sh
```
* Conteúdo do script:
 ```bash
 #!/bin/bash
aws s3 cp /home/ec2-user/sysops-activity-files/static-website/ s3://seu-bucket-nome-aqui/ --recursive --acl public-read
 ```
* Tornar executável:
 ```bash
 chmod +x update-website.sh
```
## 
🎨 7. Atualização do site

# Edição do index.html para alterar cores:
 ```bash
  vi sysops-activity-files/static-website/index.html
```
* Mudanças realizadas:
```bash
 bgcolor="aquamarine" → bgcolor="gainsboro"
bgcolor="orange" → bgcolor="cornsilk"
segunda linha bgcolor="aquamarine" → bgcolor="gainsboro"
```
* Execução do script para atualizar o site:
```bash
 ./update-website.sh
```
##
🌍 8. Visualização do site

* No Console S3 → bucket → Propriedades → Hospedagem de site estático.

* Copiar e abrir o endpoint gerado.

* Site atualizado disponível publicamente!
##
💡 Resultado

✅ Foi possível hospedar um site estático completo no Amazon S3.
✅ O upload e atualização dos arquivos foram automatizados via script shell.
✅ O laboratório reforçou conceitos de:

* Configuração de buckets públicos

* Permissões e políticas IAM

* Uso da AWS CLI

* Automação com scripts Bash
###
📚 Conclusão:

O exercício demonstrou na prática como integrar S3, IAM e EC2 para uma entrega de conteúdo web automatizada, segura e escalável.

<img width="240" height="180" alt="image" src="https://github.com/user-attachments/assets/e86b9a4b-6ca6-4ae4-bc94-517d2a9b84fa" />
