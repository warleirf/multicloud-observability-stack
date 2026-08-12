# 📊 Multi-Cloud Observability Stack (AWS + Azure + GCP + OCI)

> Solução containerizada e automatizada de **Observabilidade Quad-Cloud** para monitoramento unificado e em tempo real de ambientes **AWS, Microsoft Azure, Google Cloud (GCP) e Oracle Cloud (OCI)**.

---

## 🏗️ Arquitetura da Solução

O projeto é 100% orquestrado via **Docker Compose**, utilizando as imagens públicas pré-configuradas e hospedadas no [Docker Hub (warleirf)](https://hub.docker.com/u/warleirf):

* **Grafana (v10.1):** Camada de visualização executiva com conectores nativos e pré-provisionados para AWS CloudWatch, Azure Monitor, GCP Cloud Monitoring, OCI Metrics e Zabbix.
* **Zabbix Server & Web (v6.4 Alpine):** Motor de alta performance para monitoramento de disponibilidade, gerenciamento de triggers e auto-descoberta (LLD).
* **PostgreSQL (v15 Alpine):** Banco de dados relacional dedicado e persistente para armazenamento do Zabbix.

---

## 📁 Estrutura do Repositório

```plaintext
multicloud-observability-stack/
├── docker-compose.yml
├── .env.example
├── .gitignore
├── README.md
└── grafana/
    └── provisioning/
        ├── datasources/
        │   └── datasources.yml
        └── plugins/



🚀 Passo a Passo para Execução Rápida
1. Clonar o Repositório
Bash
git clone [https://github.com/warleirf/multicloud-observability-stack.git](https://github.com/warleirf/multicloud-observability-stack.git)
cd multicloud-observability-stack
2. Configurar Variáveis de Ambiente
Copie o arquivo de modelo e crie o seu arquivo .env:

Bash
cp .env.example .env
Nota: Edite o arquivo .env preenchendo as senhas do banco de dados, acesso ao Grafana e as credenciais das suas contas Cloud (AWS, Azure, GCP, OCI).

3. Iniciar a Stack via Docker Compose
Rode o comando abaixo para baixar as imagens diretamente do Docker Hub e iniciar os containers em segundo plano:

docker compose up -d
🌐 Endereços de Acesso
Grafana Dashboards: http://localhost:3000

Usuário: Configurado em GF_SECURITY_ADMIN_USER no .env (Padrão: admin)
Senha: Configurada em GF_SECURITY_ADMIN_PASSWORD no .env

Zabbix Web Console: http://localhost:8080
Usuário: Admin
Senha: zabbix

🛠️ Gerenciamento do Ambiente
Acompanhar os logs em tempo real:

docker compose logs -f
Parar a aplicação mantendo os dados salvos:

docker compose stop
Derrubar e remover containers/redes:

docker compose down
🔗 Links e Recursos
Portfólio Oficial: warlei.com.br


Docker Hub: hub.docker.com/u/warleirf
GitHub: github.com/warleirf
