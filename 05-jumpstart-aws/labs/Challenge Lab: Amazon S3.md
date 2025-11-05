# ☁️ Challenge Lab: Amazon S3 - Visão Geral e Conclusão

Este laboratório de desafio consistiu na criação e manipulação de um bucket no Amazon Simple Storage Service (Amazon S3) usando o Console de Gerenciamento da AWS e a AWS Command Line Interface (AWS CLI), focando em tarefas rotineiras como upload de objetos, configuração de acesso público e listagem de conteúdo.

<img width="225" height="225" alt="image" src="https://github.com/user-attachments/assets/63dc07d2-c0da-48aa-91f8-333ab753d234" />


---

## 🎯 Objetivo

O objetivo principal deste desafio foi **dominar as operações fundamentais do Amazon S3**, incluindo a criação de um bucket, o upload de um objeto e, crucialmente, a configuração de permissões de objeto para torná-lo acessível ao público, simulando a distribuição de conteúdo estático.

---

## 🪜 Passos

As seguintes tarefas foram executadas para completar o desafio:

### 1. Conexão e Configuração da AWS CLI

A conexão foi estabelecida com a instância `CLI Host`, seguida pela configuração do perfil da AWS CLI:

```bash
# 1. Conexão via EC2 Instance Connect (SSH)
# 2. Configuração do perfil:
aws configure

# Valores inseridos:
# AWS Access Key ID: <SUA ACCESS KEY>
# AWS Secret Access Key: <SUA SECRET KEY>
# Default region name: us-west-2
# Default output format: json
```
### 2. Criação do Bucket do S3
Um novo bucket foi criado na região us-west-2.


```bash
# Comando para criar o bucket
# Substitua o placeholder pelo nome do seu bucket (deve ser único globalmente)
aws s3 mb s3://<SEU-NOME-DO-BUCKET-UNICO> --region us-west-2
```
Nome do Bucket Usado: <SEU-NOME-DO-BUCKET-UNICO>

##

3. Upload do Objeto
Um arquivo de teste (testfile.txt) foi criado e carregado para o bucket.

```bash
# Criação do arquivo de teste:
echo "Este e um objeto de teste para o lab S3." > testfile.txt

# Comando para fazer upload do objeto:
aws s3 cp testfile.txt s3://<SEU-NOME-DO-BUCKET-UNICO>/testfile.txt
```
4. Configuração de Acesso Público do Objeto
Para tornar o objeto acessível, foi necessário primeiro desativar o Bloqueio de Acesso Público no nível do bucket (via Console) e, em seguida, aplicar uma ACL pública ao objeto.

```bash
# Comando para modificar o ACL do objeto e torná-lo público para leitura (public-read)
aws s3api put-object-acl --bucket <SEU-NOME-DO-BUCKET-UNICO> --key testfile.txt --acl public-read
```
5. Acesso e Validação
O objeto foi acessado com sucesso através do navegador, confirmando a aplicação correta das permissões.

URL de Acesso Público: http://<SEU-NOME-DO-BUCKET-UNICO>.s3.us-west-2.amazonaws.com/testfile.txt

6. Listagem do Conteúdo com a AWS CLI
O conteúdo do bucket foi listado para verificação final usando o comando ls.

```bash
# Comando para listar o conteúdo do bucket
aws s3 ls s3://<SEU-NOME-DO-BUCKET-UNICO>/
```

💡 Resultado
O laboratório foi concluído com sucesso. Foi demonstrada a capacidade de gerenciar o ciclo de vida básico de dados no Amazon S3, desde a criação do bucket até a configuração de acesso público a um objeto.

*  Principal Aprendizado: A importância das configurações de segurança padrão do S3. A desativação do Bloqueio de Acesso Público (Public Access Block) no bucket é o primeiro passo, mas é a aplicação explícita da ACL public-read ao objeto que concede o acesso público de leitura.

*  Habilidades Praticadas: Uso de comandos de alto nível (aws s3) e comandos de API de baixo nível (aws s3api) na AWS CLI.
