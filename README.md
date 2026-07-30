# -AWS-VPC-Lab-Bastion-Host-NAT-Gateway-Architecture
Segurança, Roteamento e Conectividade de Instâncias Privadas à Internet.

Lab: Bastion Host & NAT Gateway

Laboratório prático de **VPC** na AWS focando em segurança, roteamento e conectividade de instâncias privadas com a internet.

## 🎯 Objetivo

Simular um cenário real de mercado em que recursos sensíveis (aplicações e bancos de dados) ficam em subnets privadas, sem exposição direta à internet, utilizando:

- **Bastion Host** (Jump Box) para acesso administrativo seguro
- **NAT Gateway** para saída controlada à internet
- **Route Tables** corretamente configuradas

## 🏗️ Arquitetura



- **Public Subnet**: Bastion Host + NAT Gateway
- **Private Subnet**: Instância de aplicação/banco
- Tráfego de saída da privada → NAT Gateway
- Acesso à privada apenas via Bastion (SSH)

## ✅ Validação de Conectividade

Na instância privada:

```bash
# Teste de conectividade
ping -c 4 google.com

# Teste de resolução DNS
nslookup google.com

# Teste de atualização (exemplo Amazon Linux)
sudo dnf update -y
