# Projeto: Meu Primeiro Site na Nuvem AWS

Este projeto demonstra a implementação de uma arquitetura web simples na AWS, com o objetivo de aplicar e solidificar conhecimentos em serviços de nuvem, infraestrutura como código (IaC), redes e versionamento.
## 🎯 Objetivo

O principal objetivo é provisionar, configurar e implantar um site estático em um ambiente de nuvem AWS, seguindo boas práticas de segurança e documentação, além de demonstrar familiaridade com o ecossistema Linux e Git.

## 🏗️ Arquitetura da Solução

A solução foi desenhada para ser simples, eficaz e alinhada com os serviços fundamentais da AWS:

*   **AWS EC2 (Elastic Compute Cloud):** Uma instância `t2.micro` (nível gratuito) foi provisionada para atuar como servidor web. O sistema operacional escolhido foi o **Amazon Linux 2**, por sua otimização para o ambiente AWS.
*   **Apache Web Server:** Instalado na instância EC2 para servir o conteúdo HTML da aplicação.
*   **Security Group:** Atua como um firewall virtual para a instância, controlando o tráfego de entrada (inbound) e saída (outbound). Foram configuradas regras para permitir:
    *   **HTTP (Porta 80):** Acesso público para visualização do site.
    *   **SSH (Porta 22):** Acesso restrito ao meu IP para administração segura do servidor.
*   **Git & GitHub:** Utilizado para todo o ciclo de vida do código:
    *   Versionamento do site (`index.html`).
    *   Criação e manutenção desta documentação (`README.md`).
    *   Deploy no servidor via `git clone`.



## 🚀 Processo de Deploy (Passo a Passo)

1.  **Provisionamento da Infraestrutura:** A instância EC2 e o Security Group foram criados e configurados através do Console da AWS.
2.  **Acesso ao Servidor:** A conexão com a instância Linux foi estabelecida de forma segura via SSH, utilizando um par de chaves (.pem).
3.  **Configuração do Ambiente:** O servidor web Apache foi instalado e inicializado na instância EC2 usando o gerenciador de pacotes `yum`.
4.  **Implantação da Aplicação:** O código-fonte do site foi clonado diretamente do repositório do GitHub para o servidor. Em seguida, o arquivo `index.html` foi movido para o diretório raiz do Apache (`/var/www/html/`).

## 🌐 Como Acessar

O site está disponível publicamente no seguinte endereço:

**[Link a ser adicionado após o deploy na AWS]**

*(Nota: Por ser um ambiente de estudos, a instância pode não estar sempre online para otimização de custos. )*

## 🛠️ Tecnologias Utilizadas

*   **Cloud Provider:** AWS
*   **Serviços AWS:** EC2, Security Groups
*   **Sistema Operacional:** Amazon Linux 2
*   **Servidor Web:** Apache
*   **Linguagens:** HTML
*   **Ferramentas:** Git, GitHub, VS Code, SSH

## 🔮 Próximos Passos e Melhorias

Este projeto é a base para futuras explorações. Os próximos passos planejados são:

*   [ ] **Containerização:** Empacotar a aplicação web com **Docker** e executá-la como um contêiner na instância EC2.
*   [ ] **Automação de Infraestrutura:** Utilizar **Terraform** ou **AWS CloudFormation** para provisionar a infraestrutura como código.
*   [ ] **CI/CD:** Criar um pipeline de integração e entrega contínua com **GitHub Actions** para automatizar o deploy a cada `push` na branch `main`.
*   [ ] **Domínio e SSL:** Configurar um domínio personalizado via **Route 53** e adicionar um certificado de segurança SSL com **AWS Certificate Manager**.

