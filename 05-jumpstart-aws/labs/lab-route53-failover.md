# 🧪 Laboratório: Roteamento de Failover de Alta Disponibilidade com Amazon Route 53

<img width="318" height="159" alt="image" src="https://github.com/user-attachments/assets/e06deb5b-4ee6-45f5-958d-e3302a0562d1" />


## 🎯 Objetivo
Configurar um **mecanismo de failover ativo/passivo** para uma aplicação web simples (site da cafeteria) utilizando o **Amazon Route 53**. O objetivo é garantir que, se a instância primária (em uma Zona de Disponibilidade - AZ) falhar, o tráfego seja automaticamente roteado para a instância secundária (em uma AZ diferente), garantindo a **Alta Disponibilidade** e a **Continuidade do Negócio**.

## 🪜 Passos
O laboratório envolveu as seguintes tarefas principais e configurações:

### 1. Confirmação dos Sites da Cafeteria
* **Recursos Iniciais:** Verificação de duas instâncias Amazon EC2 (`CafeInstance1` e `CafeInstance2`), cada uma rodando a aplicação web (pilha LAMP e site da cafeteria) em Zonas de Disponibilidade (AZs) distintas (ex: `us-west-2a` e `us-west-2b`).
* **URLs Testadas:** Confirmação de que `PrimaryWebSiteURL` e `SecondaryWebsiteURL` estavam funcionais e hospedados em servidores diferentes.

### 2. Configuração da Health Check do Route 53
* **Criação do Health Check:** Configurado um *Health Check* chamado `Primary-Website-Health` para monitorar o **endpoint HTTP** da instância primária (`CafeInstance1IPAddress`).
    * **Endpoint:** Monitoramento por **Endereço IP** (`CafeInstance1IPAddress`).
    * **Caminho:** `/cafe`.
    * **Configuração Avançada:** `Intervalo de solicitações` **Rápido** (10 segundos) e `Limite de falha` **2** para detecção rápida de falha.
* **Configuração de Notificação (SNS):** Criação de um alarme e um **Novo Tópico do SNS** (`Primary-Website-Health`) para enviar alertas por e-mail quando o status de integridade mudar para **Não Íntegro**.
* **Confirmação:** Confirmação da inscrição no tópico do SNS via e-mail.

### 3. Configuração dos Registros de Failover (Zona Hospedada)
Configuração de dois registros `A` (`www.XXXXXX_XXXXXXXXXX.vocareum.training`) com a **Política de Roteamento de Failover**.

| Registro | Tipo de Registro de Failover | Valor (IP) | Health Check ID | ID do Registro |
| :--- | :--- | :--- | :--- | :--- |
| **Primário** | Primário | `CafeInstance1IPAddress` | `Primary-Website-Health` | `FailoverPrimary` |
| **Secundário** | Secundário | `CafeInstance2IPAddress` | *(Em branco)* | `FailoverSecondary` |
* **TTL (Time-to-Live):** Definido como **15 segundos** para propagação rápida de alterações do DNS.

### 4. Verificação da Resolução de DNS
* **Teste Inicial:** Acesso ao `http://www.XXXXXX_XXXXXXXXXX.vocareum.training/cafe/` no navegador.
* **Resultado:** O tráfego foi resolvido corretamente para o endereço IP do registro **Primário** (`CafeInstance1`), confirmando a Zona de Disponibilidade inicial (ex: `us-west-2a`).

### 5. Verificação da Funcionalidade do Failover
* **Simulação de Falha:** `CafeInstance1` (Primária) foi **interrompida** manualmente no console do Amazon EC2 para simular uma falha do servidor.
* **Monitoramento:** Acompanhamento do `Primary-Website-Health` no console do Route 53 até que o status mudasse para **Não Íntegro**.
* **Teste de Failover:** Recarregamento da página `http://www.XXXXXX_XXXXXXXXXX.vocareum.training/cafe/` no navegador.
* **Resultado:**
    * O site carregou e a seção **Informações do servidor** mostrou que a aplicação estava sendo servida pela instância **Secundária** (`CafeInstance2`), em uma Zona de Disponibilidade diferente (ex: `us-west-2b`).
    * Um e-mail de notificação de alarme (`ALARM: Primary-Website-Health-awsroute53-...`) foi recebido, confirmando o acionamento do SNS devido à falha do Health Check.

---

## 💡 Resultado
Este laboratório demonstrou com sucesso a implementação de um sistema de Alta Disponibilidade utilizando o **Amazon Route 53 Failover Routing**.

* **Configuração Completa:** Foi estabelecida uma política de roteamento ativo/passivo.
* **Detecção Rápida:** O *Health Check* configurado com um limite de falha de 2 e intervalo de 10 segundos garantiu a rápida detecção de indisponibilidade da instância primária.
* **Failover Automático:** O sistema de DNS do Route 53 **automaticamente** re-roteou o tráfego para a instância secundária quando o *Health Check* da primária falhou, comprovando a eficácia do plano de failover entre Zonas de Disponibilidade distintas.
* **Notificação Imediata:** A integração com o Amazon SNS assegurou que as equipes relevantes fossem notificadas da falha através de e-mail.

O resultado final é uma arquitetura **resiliente** capaz de mitigar a indisponibilidade de um único servidor ou Zona de Disponibilidade.

<img width="703" height="345" alt="image" src="https://github.com/user-attachments/assets/6bdcc303-8757-45dc-9a9f-db6607e87fd8" />
