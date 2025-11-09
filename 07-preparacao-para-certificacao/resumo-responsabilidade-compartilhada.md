# 🛡️ Modelo de Responsabilidade Compartilhada (Resumo)

Este arquivo detalha as responsabilidades da AWS e do Cliente, que é um dos tópicos mais importantes do exame CLF-C01.

---

## 1. Princípio Fundamental

| **Responsabilidade da AWS** (Segurança *DA* Nuvem) | **Responsabilidade do Cliente** (Segurança *NA* Nuvem) |
| :--- | :--- |
| **Infraestrutura Global:** Hardware, software, rede, e instalações que executam os serviços. | **Configuração e Dados:** Dados do cliente, gerenciamento de identidade e acesso (IAM), e configuração de firewalls. |
| **Proteção Física:** Segurança dos data centers, cabos e servidores. | **Segurança de Componentes Acima da AWS:** Sistemas operacionais, plataformas e aplicativos. |

---

## 2. Divisão de Responsabilidade por Modelo de Serviço

A responsabilidade do cliente aumenta à medida que o modelo de serviço se move de SaaS para IaaS.

| Modelo de Serviço | Responsabilidade do Cliente (NA Nuvem) | Exemplo de Serviço |
| :--- | :--- | :--- |
| **IaaS** (Infrastructure as a Service) | **Tudo acima do SO Host:** Sistema Operacional Convidado (Guest OS), Patches, Configuração de Rede (SG, NACL), Dados e Criptografia. | Amazon EC2 |
| **PaaS** (Platform as a Service) | **Aplicativos e Dados:** Código do Aplicativo, Criptografia, e Acesso. A AWS gerencia o SO e os Patches. | Amazon RDS, AWS Elastic Beanstalk |
| **SaaS** (Software as a Service) | **Mínima (Acesso e Dados):** Gerenciamento de Acesso ao Serviço (IAM), e Criptografia dos dados inseridos. A AWS gerencia quase tudo. | Amazon S3 (para a durabilidade do objeto), Amazon WorkDocs |
