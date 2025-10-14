# 🔒 Módulo 03: Segurança

## 📖 Descrição
Este diretório contém os resumos, anotações e práticas referentes ao módulo **Segurança** do programa AWS re/Start.  
O foco é consolidar conceitos teóricos e aplicar práticas de segurança no ambiente AWS, incluindo IAM, políticas, permissões e boas práticas.

---

## 🧠 Conteúdos Principais
- Conceitos teóricos de segurança na AWS
- Exercícios práticos com AWS Console e CLI
- Laboratórios aplicando políticas de usuários, grupos e permissões IAM

---

## 🧩 Estrutura da Pasta
- `labs/` → atividades práticas realizadas, incluindo scripts e screenshots  


---

## ✍️ Nota Pessoal

Durante o módulo de Segurança, percebi que **o controle de acesso é essencial** para proteger recursos na AWS.  
Aprendi que **grupos IAM são mais eficientes que permissões individuais**, permitindo aplicar regras em larga escala de forma consistente.  

A política de senhas é um ponto crítico: **comprimento mínimo, complexidade e expiração** aumentam a segurança contra ataques de força bruta.  

Testes práticos com diferentes usuários mostraram a importância do **princípio do Least Privilege** — cada usuário só deve ter acesso estritamente necessário para sua função.  

Ferramentas como **CloudTrail** e **CloudWatch** são fundamentais para auditoria e monitoramento, mesmo que o usuário não tenha permissão direta para algumas ações, ajudando a detectar tentativas de acesso indevido.
