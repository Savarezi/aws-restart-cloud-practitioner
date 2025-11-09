# 🧪 Simulados AWS Cloud Practitioner (60 Questões de Prática)
<img width="324" height="155" alt="image" src="https://github.com/user-attachments/assets/ead1fbfe-c904-471b-aaa9-d4f65270b77b" />


Este arquivo contém **60 questões** (15 por domínio) com respostas corretas e explicações detalhadas.
Use-o como um teste prático de revisão dos conceitos principais da certificação **AWS Certified Cloud Practitioner (CLF-C01)**.

---
## ✅ Domínio: Cloud Concepts (26%)

### Questão 1
**Pergunta:** Qual dos seguintes é o principal benefício de migrar de um modelo de Despesa de Capital (CapEx) para um modelo de Despesa Operacional (OpEx) usando a AWS Cloud?
- A) A capacidade de usar hardware dedicado sem custos de manutenção.
- B) A eliminação de custos iniciais fixos, pagando apenas pelo que se consome. ✅
- C) Redução dos requisitos de conformidade com padrões de segurança.
- D) A exclusão total da responsabilidade de segurança do cliente.

**Resposta Correta:** B) A eliminação de custos iniciais fixos, pagando apenas pelo que se consome.
**Explicação:** O modelo OpEx (Despesa Operacional) da AWS, conhecido como pagamento conforme o uso (*pay-as-you-go*), permite que as empresas evitem grandes investimentos iniciais em infraestrutura (CapEx) e transformem esses custos em despesas operacionais flexíveis baseadas no consumo real.

### Questão 2
**Pergunta:** Um usuário deseja implantar um aplicativo com alta disponibilidade e tolerância a falhas. Como a infraestrutura global da AWS ajuda a alcançar esse objetivo?
- A) Oferecendo locais de borda (Edge Locations) para processamento de dados.
- B) Usando Zonas de Disponibilidade (Availability Zones) separadas e isoladas em uma Região. ✅
- C) Permitindo o uso do AWS Billing Dashboard para monitorar custos.
- D) Fornecendo acesso ilimitado a todos os serviços da AWS gratuitamente.

**Resposta Correta:** B) Usando Zonas de Disponibilidade (Availability Zones) separadas e isoladas em uma Região.
**Explicação:** As Zonas de Disponibilidade (AZs) são data centers isolados fisicamente, mas conectados por links de baixa latência dentro de uma única Região. Distribuir recursos entre múltiplas AZs garante que se uma falha ocorrer em uma AZ, o aplicativo continue funcionando nas outras, promovendo alta disponibilidade e tolerância a falhas.

### Questão 3
**Pergunta:** Qual dos seguintes é um benefício de design fundamental do AWS Cloud que permite que um aplicativo lide com um aumento inesperado na demanda de tráfego, ajustando automaticamente os recursos?
- A) Segurança.
- B) Elasticidade. ✅
- C) Custo Fixo.
- D) Latência.

**Resposta Correta:** B) Elasticidade.
**Explicação:** A Elasticidade é a capacidade de um sistema de escalar recursos rapidamente e automaticamente (tanto para cima quanto para baixo) em resposta a mudanças na demanda, sem necessidade de intervenção manual ou de provisionar excessivamente (over-provisioning).

### Questão 4
**Pergunta:** Em qual modelo de serviço de cloud computing o cliente é responsável pelo sistema operacional, dados, aplicativos e tempo de execução, enquanto a AWS gerencia a infraestrutura subjacente?
- A) Software as a Service (SaaS).
- B) Platform as a Service (PaaS). ✅
- C) Infrastructure as a Service (IaaS).
- D) Functions as a Service (FaaS).

**Resposta Correta:** B) Platform as a Service (PaaS).
**Explicação:** No PaaS (ex: Amazon RDS, AWS Elastic Beanstalk), a AWS gerencia a infraestrutura, o sistema operacional e o tempo de execução. O cliente é responsável pelo código do aplicativo e pelos dados. No IaaS (ex: Amazon EC2), o cliente gerencia o SO.

### Questão 5
**Pergunta:** Qual dos pilares do AWS Well-Architected Framework visa usar os recursos de computação de forma eficiente e manter a infraestrutura global necessária para atender aos requisitos de carga?
- A) Segurança.
- B) Excelência Operacional.
- C) Eficiência de Desempenho. ✅
- D) Otimização de Custos.

**Resposta Correta:** C) Eficiência de Desempenho.
**Explicação:** O pilar de Eficiência de Desempenho (Performance Efficiency) concentra-se em selecionar os tipos de recursos e tecnologias mais adequados para a carga de trabalho, garantindo a eficiência do uso e mantendo a capacidade.

### Questão 6
**Pergunta:** Um cliente decide executar um aplicativo em contêineres na AWS, mas quer manter seu sistema de gerenciamento de banco de dados no seu data center local. Qual modelo de implantação de cloud ele está utilizando?
- A) Nuvem Pública (Public Cloud).
- B) Nuvem Híbrida (Hybrid Cloud). ✅
- C) Nuvem Privada (Private Cloud).
- D) Nuvem Comunitária (Community Cloud).

**Resposta Correta:** B) Nuvem Híbrida (Hybrid Cloud).
**Explicação:** Uma Nuvem Híbrida é uma arquitetura que combina recursos da nuvem pública (AWS) com recursos no local (*on-premises* ou nuvem privada), permitindo que dados e aplicativos se movam entre eles.

### Questão 7
**Pergunta:** Qual termo descreve a capacidade de um sistema aumentar ou diminuir a capacidade de forma fácil e automática para atender a uma demanda variável e imprevisível?
- A) Agilidade.
- B) Economias de Escala.
- C) Elasticidade. ✅
- D) Alta Disponibilidade.

**Resposta Correta:** C) Elasticidade.
**Explicação:** Elasticidade é o termo usado para descrever o ajuste automático e dinâmico da capacidade (escalar para cima ou para baixo) para corresponder à demanda de recursos em tempo real.

### Questão 8
**Pergunta:** Qual dos seguintes é um exemplo de despesa operacional (OpEx) na AWS?
- A) Compra de servidores físicos.
- B) Pagamento mensal pelo uso de instâncias Amazon EC2. ✅
- C) Construção de um novo data center.
- D) Licença de software vitalícia.

**Resposta Correta:** B) Pagamento mensal pelo uso de instâncias Amazon EC2.
**Explicação:** O pagamento pelo uso de serviços da AWS é uma despesa operacional (OpEx), pois é um custo variável e contínuo, ao contrário das despesas de capital (CapEx), que são custos iniciais de ativos fixos.

### Questão 9
**Pergunta:** Qual serviço da AWS oferece um firewall de aplicativo web (WAF) que protege aplicativos web de ataques comuns?
- A) AWS Shield.
- B) AWS WAF. ✅
- C) AWS GuardDuty.
- D) Amazon Inspector.

**Resposta Correta:** B) AWS WAF.
**Explicação:** O AWS WAF (Web Application Firewall) permite monitorar as solicitações HTTP e HTTPS encaminhadas para o Amazon CloudFront, Application Load Balancer ou API Gateway e controlar o acesso ao conteúdo.

### Questão 10
**Pergunta:** O que são Locais de Borda (Edge Locations) no contexto da AWS Global Infrastructure?
- A) Data centers que hospedam os serviços de computação e armazenamento de uma Região.
- B) Sites usados pelo Amazon Route 53 e Amazon CloudFront para armazenamento em cache de conteúdo e roteamento de DNS. ✅
- C) Locais onde a AWS faz a cobrança e o faturamento dos clientes.
- D) Uma infraestrutura de computação local para clientes que não podem ir para a nuvem.

**Resposta Correta:** B) Sites usados pelo Amazon Route 53 e Amazon CloudFront para armazenamento em cache de conteúdo e roteamento de DNS.
**Explicação:** Edge Locations são pontos de presença globais que entregam conteúdo em cache mais perto dos usuários finais, melhorando a performance e reduzindo a latência, principalmente com o CloudFront (CDN).

### Questão 11
**Pergunta:** Qual dos seguintes modelos de serviço de nuvem é o mais gerenciado pela AWS, onde o cliente usa o aplicativo final sem gerenciar a infraestrutura subjacente?
- A) Infrastructure as a Service (IaaS).
- B) Platform as a Service (PaaS).
- C) Software as a Service (SaaS). ✅
- D) Container as a Service (CaaS).

**Resposta Correita:** C) Software as a Service (SaaS).
**Explicação:** No modelo SaaS (ex: Amazon WorkDocs, Amazon Sagemaker), o cliente apenas consome o software. A AWS é responsável por gerenciar tudo, desde a infraestrutura até o aplicativo em si.

### Questão 12
**Pergunta:** Qual o benefício de ter várias Regiões geográficas na AWS?
- A) A capacidade de usar instâncias Amazon EC2 sem custo.
- B) A capacidade de hospedar workloads perto de usuários globais para reduzir a latência. ✅
- C) A eliminação completa do modelo de responsabilidade compartilhada.
- D) A exclusão da necessidade de usar grupos de segurança.

**Resposta Correta:** B) A capacidade de hospedar workloads perto de usuários globais para reduzir a latência.
**Explicação:** As Regiões permitem que os clientes escolham um local geográfico para seus dados e aplicativos, o que ajuda a atender aos requisitos de soberania de dados, conformidade e, principalmente, reduzir a latência para os usuários finais naquela área.

### Questão 13
**Pergunta:** Qual dos seguintes princípios de design da AWS enfatiza a construção de sistemas que possam se recuperar automaticamente de falhas sem impacto no cliente?
- A) Mantenha a capacidade de escala.
- B) Pague por capacidade de computação em excesso.
- C) Projete para falhas. ✅
- D) Use servidores dedicados.

**Resposta Correita:** C) Projete para falhas.
**Explicação:** Projetar para falhas (*Design for Failure*) significa assumir que as falhas ocorrerão e implementar redundância (por exemplo, usando várias Zonas de Disponibilidade) para que o sistema permaneça funcional quando os componentes falharem.

### Questão 14
**Pergunta:** Um desenvolvedor precisa de uma maneira de usar o poder de processamento da AWS sem precisar provisionar ou gerenciar servidores. Qual serviço de computação serverless ele deve usar?
- A) Amazon EC2.
- B) Amazon EBS.
- C) AWS Lambda. ✅
- D) Amazon S3.

**Resposta Correita:** C) AWS Lambda.
**Explicação:** O AWS Lambda é um serviço de computação serverless (sem servidor) que permite aos desenvolvedores executar código em resposta a eventos sem ter que provisionar ou gerenciar a infraestrutura de servidores.

### Questão 15
**Pergunta:** Qual pilar do Well-Architected Framework visa usar a tecnologia de forma a permitir que a equipe alcance metas de negócios e melhorias contínuas nos procedimentos?
- A) Otimização de Custos.
- B) Segurança.
- C) Confiabilidade.
- D) Excelência Operacional. ✅

**Resposta Correita:** D) Excelência Operacional.
**Explicação:** O pilar de Excelência Operacional concentra-se na execução e monitoramento de sistemas para fornecer valor de negócios e melhorar continuamente os processos e procedimentos de suporte.

---
## ✅ Domínio: Security & Compliance (25%)

### Questão 16
**Pergunta:** De acordo com o Modelo de Responsabilidade Compartilhada da AWS, qual item é de responsabilidade **EXCLUSIVA** do cliente?
- A) Segurança da rede global da AWS.
- B) Segurança física do data center da AWS.
- C) Patching do sistema operacional de uma instância Amazon EC2. ✅
- D) Segurança do hardware e da infraestrutura.

**Resposta Correita:** C) Patching do sistema operacional de uma instância Amazon EC2.
**Explicação:** No Modelo de Responsabilidade Compartilhada, a AWS é responsável pela *Segurança da Nuvem* (hardware, infraestrutura, Regiões, Zonas de Disponibilidade). O cliente é responsável pela *Segurança NA Nuvem*, o que inclui a configuração de firewalls (Security Groups), dados, e, no caso de IaaS (como o EC2), o sistema operacional.

### Questão 17
**Pergunta:** Qual serviço da AWS pode ser usado para monitorar e registrar a atividade da conta, registrando todas as chamadas de API feitas por ou em nome da sua conta AWS?
- A) Amazon CloudWatch.
- B) AWS CloudTrail. ✅
- C) AWS Config.
- D) Amazon Inspector.

**Resposta Correita:** B) AWS CloudTrail.
**Explicação:** O AWS CloudTrail é o serviço que fornece governança, conformidade e auditoria para a sua conta, registrando as chamadas de API da AWS para rastrear ações realizadas por usuários, funções e serviços.

### Questão 18
**Pergunta:** Qual ferramenta de segurança da AWS escaneia continuamente sua conta em busca de credenciais de acesso não utilizadas, falta de MFA (Autenticação Multifator) e portas inseguras?
- A) AWS Shield.
- B) AWS Secrets Manager.
- C) AWS Trusted Advisor. ✅
- D) Amazon GuardDuty.

**Resposta Correita:** C) AWS Trusted Advisor.
**Explicação:** O Trusted Advisor fornece orientações e verificações em cinco categorias, sendo uma delas a Segurança. Ele alerta sobre configurações que podem expor sua conta a riscos, como portas abertas para o mundo ou falta de MFA na conta root.

### Questão 19
**Pergunta:** Qual dos seguintes serviços permite definir permissões granulares para quem pode acessar quais recursos (usuários, grupos, roles) em sua conta AWS?
- A) Amazon S3.
- B) AWS IAM. ✅
- C) Amazon CloudFront.
- D) Amazon VPC.

**Resposta Correita:** B) AWS IAM (Identity and Access Management).
**Explicação:** O AWS IAM é o serviço de identidade e acesso que permite gerenciar usuários e definir, por meio de políticas, quem tem permissão para acessar e usar recursos da AWS.

### Questão 20
**Pergunta:** Como um cliente pode garantir que as credenciais de sua conta root sejam mais seguras, seguindo as melhores práticas de segurança da AWS?
- A) Usando as credenciais root diariamente para tarefas administrativas.
- B) Armazenando as chaves de acesso root em um bucket do S3.
- C) Excluindo o usuário root após criar um usuário IAM administrativo.
- D) Configurando Autenticação Multifator (MFA) na conta root e usando-a apenas para tarefas essenciais. ✅

**Resposta Correita:** D) Configurando Autenticação Multifator (MFA) na conta root e usando-a apenas para tarefas essenciais.
**Explicação:** A melhor prática é proteger a conta root com MFA e usá-la apenas para tarefas que **exigem** o usuário root (como alterar o plano de suporte), delegando tarefas diárias a usuários IAM administrativos.

### Questão 21
**Pergunta:** Para proteger seus aplicativos web de ataques comuns como injeção de SQL e Cross-Site Scripting (XSS), qual serviço da AWS você deve usar?
- A) Amazon GuardDuty.
- B) AWS WAF. ✅
- C) AWS Shield Advanced.
- D) Amazon Inspector.

**Resposta Correita:** B) AWS WAF (Web Application Firewall).
**Explicação:** O AWS WAF permite monitorar solicitações HTTP/HTTPS e bloquear automaticamente tráfego malicioso que corresponda a regras definidas, incluindo padrões de ataques conhecidos de aplicativos web.

### Questão 22
**Pergunta:** Qual é a principal função de um Security Group na AWS?
- A) Agir como um firewall no nível da sub-rede para controlar o tráfego de entrada e saída.
- B) Agir como um firewall no nível da instância para controlar o tráfego de entrada e saída. ✅
- C) Prover isolamento lógico entre redes de clientes.
- D) Rastrear todas as chamadas de API da AWS.

**Resposta Correita:** B) Agir como um firewall no nível da instância para controlar o tráfego de entrada e saída.
**Explicação:** Um Security Group é um firewall com estado que controla o tráfego em nível de instância (EC2). As regras de entrada e saída se aplicam a todas as instâncias associadas a ele.

### Questão 23
**Pergunta:** Qual das seguintes opções é um benefício de Segurança do AWS Cloud?
- A) Eliminação da necessidade de criptografar dados.
- B) Eliminação da necessidade de gerenciar o sistema operacional.
- C) O cliente se beneficia automaticamente dos padrões de segurança física de classe mundial da AWS. ✅
- D) A AWS assume a responsabilidade de auditar a conformidade de todos os dados do cliente.

**Resposta Correita:** C) O cliente se beneficia automaticamente dos padrões de segurança física de classe mundial da AWS.
**Explicação:** A AWS gerencia a segurança física de seus data centers, o que significa que o cliente herda automaticamente esse benefício de segurança sem custo adicional ou esforço.

### Questão 24
**Pergunta:** Qual serviço da AWS monitora continuamente a atividade maliciosa e o comportamento não autorizado para proteger contas e workloads da AWS?
- A) AWS CloudFormation.
- B) Amazon GuardDuty. ✅
- C) AWS CloudTrail.
- D) Amazon S3.

**Resposta Correita:** B) Amazon GuardDuty.
**Explicação:** O GuardDuty é um serviço de detecção de ameaças que usa aprendizado de máquina, inteligência de ameaças e monitoramento de logs para identificar ameaças e anomalias na conta AWS.

### Questão 25
**Pergunta:** Para proteger o tráfego web de ataques DDoS massivos, qual serviço deve ser usado?
- A) Amazon Inspector.
- B) AWS Shield. ✅
- C) AWS KMS.
- D) Amazon SES.

**Resposta Correita:** B) AWS Shield.
**Explicação:** O AWS Shield é um serviço de proteção contra DDoS (Distributed Denial of Service) que protege aplicativos em execução na AWS. O Shield Standard é gratuito e ativado por padrão.

### Questão 26
**Pergunta:** O que é uma AWS Role (Função da AWS)?
- A) Uma identidade de usuário com credenciais de longo prazo.
- B) Uma lista de permissões que só pode ser anexada a um grupo.
- C) Uma identidade que pode ser assumida temporariamente por um usuário ou serviço para obter permissões. ✅
- D) Um tipo de Security Group usado para servidores de banco de dados.

**Resposta Correita:** C) Uma identidade que pode ser assumida temporariamente por um usuário ou serviço para obter permissões.
**Explicação:** Um AWS Role é uma identidade IAM que não possui credenciais de longo prazo (como senha ou chave de acesso), mas que pode ser assumida por um usuário, serviço da AWS (como EC2 ou Lambda) ou aplicativo para conceder permissões temporárias e necessárias.

### Questão 27
**Pergunta:** Qual serviço da AWS ajuda você a avaliar automaticamente a vulnerabilidade e o desvio de configurações de suas instâncias EC2 e aplicativos?
- A) AWS Config.
- B) Amazon Inspector. ✅
- C) Amazon CloudWatch.
- D) AWS WAF.

**Resposta Correita:** B) Amazon Inspector.
**Explicação:** O Amazon Inspector é um serviço automatizado de gerenciamento de vulnerabilidades que escaneia continuamente as cargas de trabalho da AWS em busca de vulnerabilidades de software e desvio das melhores práticas.

### Questão 28
**Pergunta:** Qual serviço deve ser usado para criptografar dados em repouso no Amazon S3 de forma mais eficaz, onde você tem controle sobre as chaves de criptografia?
- A) Criptografia do lado do servidor com chaves S3 (SSE-S3).
- B) Criptografia do lado do servidor com chaves KMS (SSE-KMS). ✅
- C) Criptografia do lado do cliente com chaves S3.
- D) Criptografia do lado do servidor com chaves fornecidas pelo cliente (SSE-C).

**Resposta Correita:** B) Criptografia do lado do servidor com chaves KMS (SSE-KMS).
**Explicação:** O SSE-KMS usa o AWS Key Management Service (KMS) para gerenciar as chaves de criptografia. Ele oferece o controle e a auditoria de acesso sobre as chaves, sendo a opção mais comum para clientes que buscam gerenciar o uso das chaves.

### Questão 29
**Pergunta:** Qual serviço da AWS ajuda a garantir que seus recursos estejam em conformidade com as regras de configuração corporativas ou regulatórias?
- A) AWS CloudTrail.
- B) AWS Config. ✅
- C) AWS Marketplace.
- D) AWS Organizations.

**Resposta Correita:** B) AWS Config.
**Explicação:** O AWS Config avalia, audita e avalia as configurações dos seus recursos da AWS. Ele monitora a conformidade das configurações e pode alertar sobre desvios (por exemplo, um Security Group aberto demais).

### Questão 30
**Pergunta:** No contexto do Modelo de Responsabilidade Compartilhada, qual dos seguintes é um exemplo da responsabilidade **DA AWS** (Segurança *da* Nuvem)?
- A) Gerenciamento de Patches no Sistema Operacional Convidado (Guest OS).
- B) Proteção e segurança do software e hardware do host (Host OS). ✅
- C) Configuração de firewall de rede (Security Groups).
- D) Criptografia de dados do cliente em trânsito.

**Resposta Correita:** B) Proteção e segurança do software e hardware do host (Host OS).
**Explicação:** A AWS é responsável por proteger a infraestrutura que executa todos os serviços da AWS, incluindo o host OS, a camada de virtualização e a segurança física. O cliente é responsável pela configuração do Guest OS (A).

---
## ✅ Domínio: Technology (33%)

### Questão 31
**Pergunta:** Qual serviço da AWS deve ser usado para hospedar um site estático altamente escalável e de baixo custo?
- A) Amazon EC2.
- B) Amazon S3. ✅
- C) Amazon RDS.
- D) AWS Lambda.

**Resposta Correita:** B) Amazon S3 (Simple Storage Service).
**Explicação:** O S3 é o serviço mais adequado para hospedar sites estáticos (HTML, CSS, JavaScript) devido à sua alta durabilidade, escalabilidade e ao recurso de hospedagem de site estático embutido, que é muito econômico.

### Questão 32
**Pergunta:** Um arquiteto precisa de um banco de dados que possa lidar com escala massiva e baixa latência sem a necessidade de definir um esquema fixo. Qual tipo de banco de dados AWS ele deve considerar?
- A) Amazon RDS.
- B) Amazon Redshift.
- C) Amazon DynamoDB. ✅
- D) Amazon Neptune.

**Resposta Correita:** C) Amazon DynamoDB.
**Explicação:** O DynamoDB é um serviço de banco de dados NoSQL totalmente gerenciado, projetado para aplicativos que precisam de performance em escala de petabytes com latência de milissegundos de um dígito. Não requer um esquema fixo (sem esquema).

### Questão 33
**Pergunta:** Qual dos serviços a seguir é uma solução de armazenamento em bloco (*block storage*) projetada para ser usada como disco rígido virtual para instâncias Amazon EC2?
- A) Amazon S3.
- B) Amazon EBS. ✅
- C) AWS Storage Gateway.
- D) Amazon Glacier.

**Resposta Correita:** B) Amazon EBS (Elastic Block Store).
**Explicação:** O EBS fornece volumes de armazenamento em bloco persistentes para serem usados com instâncias EC2, atuando como um disco rígido do sistema operacional ou um disco de dados adicional.

### Questão 34
**Pergunta:** Um usuário precisa de um banco de dados relacional (MySQL, PostgreSQL) que seja totalmente gerenciado pela AWS, incluindo aplicação de patches, backups e alta disponibilidade. Qual serviço ele deve escolher?
- A) Amazon EC2 com MySQL instalado manualmente.
- B) Amazon DynamoDB.
- C) Amazon RDS. ✅
- D) Amazon Redshift.

**Resposta Correita:** C) Amazon RDS (Relational Database Service).
**Explicação:** O Amazon RDS é um serviço que facilita a configuração, operação e escala de bancos de dados relacionais na nuvem, automatizando tarefas de administração para que o cliente se concentre no aplicativo.

### Questão 35
**Pergunta:** Qual serviço da AWS é uma rede de entrega de conteúdo (CDN) que distribui conteúdo para locais de borda em todo o mundo para reduzir a latência?
- A) Amazon Route 53.
- B) AWS Direct Connect.
- C) Amazon CloudFront. ✅
- D) Amazon VPC.

**Resposta Correita:** C) Amazon CloudFront.
**Explicação:** O CloudFront é um CDN (Content Delivery Network) que usa Edge Locations (Locais de Borda) para armazenar cópias em cache de conteúdo estático e dinâmico, entregando-o aos usuários com menor latência.

### Questão 36
**Pergunta:** Qual recurso da Amazon VPC permite controlar o tráfego de entrada e saída para uma sub-rede inteira, funcionando como um firewall sem estado?
- A) Security Group.
- B) Network Access Control List (NACL). ✅
- C) Internet Gateway.
- D) NAT Gateway.

**Resposta Correita:** B) Network Access Control List (NACL).
**Explicação:** Uma NACL é um firewall sem estado que opera no nível da sub-rede. Ao contrário dos Security Groups (com estado, nível de instância), a NACL deve ter regras de entrada e saída definidas explicitamente para permitir o tráfego de retorno.

### Questão 37
**Pergunta:** Qual serviço permite criar instâncias virtuais (máquinas virtuais) na AWS?
- A) Amazon S3.
- B) Amazon EC2. ✅
- C) Amazon Lambda.
- D) Amazon Route 53.

**Resposta Correita:** B) Amazon EC2 (Elastic Compute Cloud).
**Explicação:** O EC2 é o principal serviço de computação que oferece capacidade de computação redimensionável na nuvem na forma de instâncias virtuais.

### Questão 38
**Pergunta:** Um desenvolvedor quer que seu código de aplicativo seja executado em resposta a gatilhos (como um arquivo sendo carregado no S3) sem se preocupar com a infraestrutura do servidor. Qual serviço de computação serverless é ideal?
- A) Amazon EC2.
- B) AWS Lambda. ✅
- C) AWS Elastic Beanstalk.
- D) Amazon ECS.

**Resposta Correita:** B) AWS Lambda.
**Explicação:** O Lambda é um serviço de computação serverless baseado em eventos, perfeito para executar código sem provisionar ou gerenciar servidores, escalando automaticamente em resposta ao volume de eventos.

### Questão 39
**Pergunta:** Qual serviço é usado para distribuir automaticamente o tráfego de entrada entre várias instâncias Amazon EC2 em uma ou mais Zonas de Disponibilidade?
- A) AWS Auto Scaling.
- B) Elastic Load Balancing (ELB). ✅
- C) Amazon Route 53.
- D) Amazon SQS.

**Resposta Correita:** B) Elastic Load Balancing (ELB).
**Explicação:** O ELB distribui o tráfego de rede para melhorar a disponibilidade e o desempenho dos aplicativos.

### Questão 40
**Pergunta:** Para criar uma regra de escalabilidade automática que adiciona instâncias Amazon EC2 quando a utilização da CPU atinge 70% e remove instâncias quando a utilização cai para 30%, qual serviço é necessário?
- A) Amazon CloudWatch.
- B) AWS Auto Scaling. ✅
- C) Elastic Load Balancing (ELB).
- D) AWS Systems Manager.

**Resposta Correita:** B) AWS Auto Scaling.
**Explicação:** O AWS Auto Scaling monitora o desempenho de seus aplicativos e ajusta automaticamente a capacidade para manter o desempenho em um nível desejado (escalar para cima ou para baixo).

### Questão 41
**Pergunta:** Qual serviço da AWS é um serviço DNS (Domain Name System) web altamente disponível e escalável?
- A) Amazon CloudFront.
- B) Amazon VPC.
- C) Amazon Route 53. ✅
- D) AWS Direct Connect.

**Resposta Correita:** C) Amazon Route 53.
**Explicação:** O Route 53 é o serviço de DNS da AWS que fornece registro de domínio, roteamento de tráfego e verificação de integridade dos recursos.

### Questão 42
**Pergunta:** Qual serviço permite modelar e provisionar recursos da AWS e de terceiros em sua infraestrutura em um modelo de código?
- A) AWS CodeDeploy.
- B) AWS CloudFormation. ✅
- C) AWS Management Console.
- D) AWS Systems Manager.

**Resposta Correita:** B) AWS CloudFormation.
**Explicação:** O CloudFormation é o serviço de *Infrastructure as Code* (IaC) da AWS, que permite descrever os recursos necessários em um arquivo de template (JSON ou YAML) e provisioná-los de forma automatizada e repetível.

### Questão 43
**Pergunta:** Qual serviço da AWS é usado para coletar métricas, logs e eventos de infraestrutura, permitindo monitorar o desempenho e definir alarmes?
- A) AWS CloudTrail.
- B) Amazon CloudWatch. ✅
- C) AWS Config.
- D) AWS Trusted Advisor.

**Resposta Correita:** B) Amazon CloudWatch.
**Explicação:** O CloudWatch é o serviço de monitoramento para recursos e aplicativos da AWS. Ele coleta e rastreia métricas e logs, e permite que você defina alarmes para tomar ações automáticas quando um limite for atingido.

### Questão 44
**Pergunta:** Para permitir conectividade de rede privada entre o seu data center local e a Amazon VPC, qual serviço oferece uma conexão de rede dedicada?
- A) Internet Gateway.
- B) NAT Gateway.
- C) AWS Direct Connect. ✅
- D) Amazon Connect.

**Resposta Correita:** C) AWS Direct Connect.
**Explicação:** O Direct Connect estabelece uma conexão de rede privada dedicada de seu data center para a AWS, reduzindo os custos de rede, aumentando a taxa de transferência e fornecendo uma experiência de rede mais consistente do que as conexões baseadas na Internet.

### Questão 45
**Pergunta:** Qual serviço de mensagens desacopla os componentes de um aplicativo usando uma fila de mensagens gerenciada?
- A) Amazon SNS (Simple Notification Service).
- B) Amazon SQS (Simple Queue Service). ✅
- C) AWS SES (Simple Email Service).
- D) AWS Connect.

**Resposta Correita:** B) Amazon SQS (Simple Queue Service).
**Explicação:** O SQS fornece uma fila de mensagens para armazenar e desacoplar componentes distribuídos, garantindo que as mensagens sejam processadas, mesmo que o componente consumidor não esteja disponível imediatamente.

---
## ✅ Domínio: Billing & Pricing (16%)

### Questão 46
**Pergunta:** Qual princípio de precificação da AWS permite que um cliente pague por capacidade de computação de forma antecipada para obter um desconto significativo, ideal para cargas de trabalho estáveis?
- A) Pay-as-you-go (Pagamento conforme o uso).
- B) Savings Plans ou Reserved Instances (Instâncias Reservadas). ✅
- C) Tier Gratuito (Free Tier).
- D) Instâncias Spot.

**Resposta Correita:** B) Savings Plans ou Reserved Instances (Instâncias Reservadas).
**Explicação:** As Instâncias Reservadas (RIs) ou, de forma mais moderna, os Savings Plans, oferecem descontos substanciais (até 72%) em troca de um compromisso de uso de longo prazo (1 ou 3 anos), sendo ideais para cargas de trabalho de estado estável e previsível.

### Questão 47
**Pergunta:** Qual serviço da AWS permite consolidar o faturamento e os pagamentos de várias contas AWS em uma única fatura?
- A) AWS Cost Explorer.
- B) AWS Budgets.
- C) AWS Organizations. ✅
- D) AWS Trusted Advisor.

**Resposta Correita:** C) AWS Organizations.
**Explicação:** O AWS Organizations permite que você gerencie e governe centralmente vários contas. O recurso de Faturamento Consolidado (*Consolidated Billing*) combina o uso de todas as contas para que você se beneficie de descontos por volume e receba uma única fatura.

### Questão 48
**Pergunta:** Qual das seguintes opções é uma característica do preço da Amazon EC2?
- A) O custo é o mesmo, independentemente da região em que a instância está localizada.
- B) Você paga pela instância mesmo quando ela está no estado 'stopped' (parada).
- C) Não há cobrança se a instância for do tipo Linux e estiver no estado 'running' (em execução).
- D) Você paga apenas pela capacidade de computação que consome, por segundo, após o primeiro minuto. ✅

**Resposta Correita:** D) Você paga apenas pela capacidade de computação que consome, por segundo, após o primeiro minuto.
**Explicação:** A precificação do EC2 segue o modelo pay-as-you-go. As instâncias são cobradas por segundo (após o primeiro minuto) para Linux ou por hora para Windows. O pagamento é interrompido quando a instância é terminada ou parada.

### Questão 49
**Pergunta:** Qual ferramenta da AWS permite visualizar e analisar seus custos e uso ao longo do tempo, e pode ser usada para prever custos futuros?
- A) AWS Budgets.
- B) AWS Cost Explorer. ✅
- C) AWS Marketplace.
- D) AWS Direct Connect.

**Resposta Correita:** B) AWS Cost Explorer.
**Explicação:** O Cost Explorer é uma ferramenta gratuita que permite visualizar, entender e gerenciar seus custos e uso da AWS ao longo do tempo. Ele é excelente para análise histórica e previsão de tendências.

### Questão 50
**Pergunta:** Um usuário está implantando um novo aplicativo na AWS e quer monitorar o consumo de recursos e ser notificado quando o uso exceder um limite predefinido. Qual ferramenta deve ser usada?
- A) AWS Trusted Advisor.
- B) AWS Budgets. ✅
- C) AWS CloudTrail.
- D) AWS Cost Explorer.

**Resposta Correita:** B) AWS Budgets.
**Explicação:** O AWS Budgets permite que você defina orçamentos personalizados para rastrear seus custos e uso da AWS. Ele pode enviar notificações quando os limites definidos (como um orçamento) forem excedidos.

### Questão 51
**Pergunta:** Qual dos seguintes fatores **NÃO** influencia o custo do Amazon S3?
- A) Volume de armazenamento.
- B) Transferência de dados (saída para a Internet).
- C) Tipo e tamanho da instância EC2 anexada ao bucket. ✅
- D) Número de solicitações (GET, PUT, etc.).

**Resposta Correita:** C) Tipo e tamanho da instância EC2 anexada ao bucket.
**Explicação:** O S3 é um serviço de armazenamento independente. O custo do S3 não é afetado por recursos de computação anexados (EC2). Os principais fatores de custo são: armazenamento, solicitações (requests) e transferência de dados para fora da AWS.

### Questão 52
**Pergunta:** Que tipo de plano de suporte da AWS oferece acesso a um Technical Account Manager (TAM) e é projetado para clientes com cargas de trabalho críticas em escala?
- A) Basic.
- B) Developer.
- C) Business.
- D) Enterprise. ✅

**Resposta Correita:** D) Enterprise.
**Explicação:** O Plano de Suporte Enterprise é o mais abrangente, oferecendo acesso a um Technical Account Manager (TAM) dedicado, que ajuda a coordenar os recursos da AWS e fornece orientação arquitetônica.

### Questão 53
**Pergunta:** O que são as Instâncias Spot do Amazon EC2?
- A) Instâncias reservadas por 3 anos com um desconto fixo.
- B) Instâncias que podem ser adquiridas com um desconto significativo, mas que podem ser interrompidas pela AWS com um aviso de 2 minutos. ✅
- C) Instâncias gratuitas para o primeiro ano de uso.
- D) Instâncias dedicadas a um único cliente.

**Resposta Correita:** B) Instâncias que podem ser adquiridas com um desconto significativo, mas que podem ser interrompidas pela AWS com um aviso de 2 minutos.
**Explicação:** As Instâncias Spot permitem que os clientes ofereçam o lance por capacidade ociosa do EC2. Elas oferecem grandes descontos, mas são adequadas apenas para cargas de trabalho flexíveis, pois podem ser interrompidas pela AWS.

### Questão 54
**Pergunta:** Qual das seguintes opções é uma ferramenta gratuita que pode ser usada para estimar o custo mensal de implantações na AWS antes de serem lançadas?
- A) AWS Cost Explorer.
- B) AWS Total Cost of Ownership (TCO) Calculator.
- C) AWS Simple Monthly Calculator (Calculadora de Preços da AWS). ✅
- D) AWS Pricing API.

**Resposta Correita:** C) AWS Simple Monthly Calculator (Calculadora de Preços da AWS).
**Explicação:** A Calculadora de Preços da AWS (anteriormente Simple Monthly Calculator) é a ferramenta que permite estimar os custos de serviços individuais ou de soluções completas na AWS.

### Questão 55
**Pergunta:** Qual dos seguintes é um benefício de usar o Faturamento Consolidado (*Consolidated Billing*) no AWS Organizations?
- A) Reduzir a latência entre contas AWS.
- B) Garantir que todas as contas estejam em conformidade com as regras de segurança.
- C) Obter descontos por volume e usar um limite de uso unificado para a Free Tier. ✅
- D) Eliminar completamente a necessidade de usar o IAM.

**Resposta Correita:** C) Obter descontos por volume e usar um limite de uso unificado para a Free Tier.
**Explicação:** O Faturamento Consolidado agrupa os custos de todas as contas, permitindo que o cliente se beneficie de preços em camadas e descontos por volume, além de usar o limite da Free Tier apenas uma vez no agregado.

### Questão 56
**Pergunta:** Qual ferramenta ajuda a planejar e comparar o custo de executar seu aplicativo *on-premises* (local) versus na AWS?
- A) AWS Simple Monthly Calculator.
- B) AWS Budgets.
- C) AWS Total Cost of Ownership (TCO) Calculator. ✅
- D) AWS Cost Explorer.

**Resposta Correita:** C) AWS Total Cost of Ownership (TCO) Calculator.
**Explicação:** O TCO Calculator é projetado para estimar e comparar o custo total de propriedade entre o ambiente local e a nuvem AWS, ajudando a justificar a migração.

### Questão 57
**Pergunta:** Qual dos seguintes serviços pode ajudar um cliente a otimizar custos, identificando recursos ociosos ou subutilizados?
- A) AWS CloudTrail.
- B) AWS Trusted Advisor. ✅
- C) AWS Organizations.
- D) Amazon SQS.

**Resposta Correita:** B) AWS Trusted Advisor.
**Explicação:** O Trusted Advisor oferece verificações nas categorias de Otimização de Custos (além de Segurança, Desempenho, Tolerância a Falhas e Limites de Serviço), alertando sobre recursos ociosos do EC2, volumes EBS subutilizados e outros itens que geram custos desnecessários.

### Questão 58
**Pergunta:** O que acontece quando o período de um ano do AWS Free Tier (Tier Gratuito) expira?
- A) Todos os recursos em execução são encerrados automaticamente.
- B) A conta é congelada até que um plano de suporte seja adquirido.
- C) Você é cobrado pelas taxas padrão *pay-as-you-go* pelos recursos que continuar a usar. ✅
- D) Sua conta é automaticamente migrada para o plano de suporte Developer.

**Resposta Correita:** C) Você é cobrado pelas taxas padrão *pay-as-you-go* pelos recursos que continuar a usar.
**Explicação:** Após a expiração ou se o limite do Free Tier for excedido, a cobrança volta automaticamente ao modelo padrão de pagamento conforme o uso.

### Questão 59
**Pergunta:** Qual é um dos principais fatores que determina o custo da transferência de dados na AWS?
- A) O custo é mais alto ao transferir dados *de* uma Região da AWS *para* a Internet. ✅
- B) O custo é mais alto ao transferir dados *para* a AWS (transferência de entrada).
- C) A transferência de dados entre regiões AWS é sempre gratuita.
- D) O custo é determinado pelo número de chamadas de API feitas.

**Resposta Correita:** A) O custo é mais alto ao transferir dados *de* uma Região da AWS *para* a Internet.
**Explicação:** A regra geral de precificação de transferência de dados da AWS é: a transferência de entrada (para a AWS) geralmente é gratuita, enquanto a transferência de saída (para a Internet) é cobrada.

### Questão 60
**Pergunta:** Qual serviço pode ser usado para aplicar uma política de otimização de custos em todas as contas de uma organização, limitando a capacidade de iniciar um tipo de instância caro?
- A) AWS Cost Explorer.
- B) AWS Service Catalog.
- C) Service Control Policies (SCPs) no AWS Organizations. ✅
- D) Amazon CloudWatch Alarms.

**Resposta Correita:** C) Service Control Policies (SCPs) no AWS Organizations.
**Explicação:** As SCPs são políticas de gerenciamento que oferecem controle centralizado sobre as permissões máximas disponíveis para todas as contas em uma Organização. Elas podem ser usadas para negar a permissão para iniciar serviços ou tipos de recursos específicos e caros.
