### AWS-VPC-Lab-Bastion-Host-NAT-Gateway-Architecture

<p align="center">
<img src="https://github.com/user-attachments/assets/f6fb8045-107e-48d5-bf47-92445c31097c" width="700">
</p>

### ☁️ AWS VPC Lab: Bastion Host & NAT Gateway

Laboratório prático de **VPC** na AWS focando em segurança, roteamento e conectividade de instâncias privadas com a internet.

### 🎯 Objetivo

Simular um cenário real de mercado em que recursos sensíveis (aplicações e bancos de dados) ficam em subnets privadas, sem exposição direta à internet, utilizando:

- **Bastion Host** (Jump Box) para acesso administrativo seguro
- **NAT Gateway** para saída controlada à internet
- **Route Tables** corretamente configuradas

### 🏗️ Arquitetura

<p align="center">
  ![Diagrama de Arquitetura](https://github.com/usuario/repositorio/blob/main/assets/sua-imagem.png)
</p>

- **Public Subnet**: Bastion Host + NAT Gateway
- **Private Subnet**: Instância de aplicação/banco
- Tráfego de saída da privada → NAT Gateway
- Acesso à privada apenas via Bastion (SSH)

### ✅ Validação de Conectividade

Na instância privada:

```bash
# Teste de conectividade
ping -c 4 google.com

# Teste de resolução DNS
nslookup google.com

# Teste de atualização (exemplo Amazon Linux)
sudo dnf update -y

Resultado obtido: 0% packet loss (Zero perda de pacotes), confirmando o sucesso do roteamento via NAT Gateway.

📸 Evidência do Laboratório
(Insira aqui a imagem gerada do seu setup ou a captura de tela do terminal com o resultado do ping)

💡 Principais Aprendizados
Configuração e associação de Tabelas de Rotas (Route Tables) na AWS.

Implementação de boas práticas de segurança utilizando Bastion Hosts para acesso SSH controlado.

Resolução de problemas de rede, diagnóstico de rotas e validação de pacotes via terminal Linux.

Desenvolvido por Eliana Diniz 🚀
