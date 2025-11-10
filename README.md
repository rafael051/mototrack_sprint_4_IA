# 🏍️ MotoTrack - Sprint 4 (FIAP 2025)

## 🎯 Descrição Geral

O **MotoTrack** é uma solução integrada e inteligente para **gestão de motos de entrega**, desenvolvida como parte do **Challenge Mottu 2025 (Sprint 4)**.  
A aplicação oferece um **monitoramento em tempo real** da frota, permitindo acompanhar:

- Localização das motos no pátio (mapa ou grid);
- Estado operacional (em uso, parada, manutenção, etc.);
- Alertas automáticos e indicadores de risco;
- Integração entre APIs, dispositivos e aplicativos móveis.

O projeto demonstra a **integração total entre disciplinas** — desde a captura de dados com IoT/Visão Computacional até a visualização final em Dashboard e App Mobile — consolidando os aprendizados técnicos e práticos do semestre.

---

## 🧩 Componentes Integrados

| Módulo | Tecnologia | Descrição |
|--------|-------------|-----------|
| **IoT / Visão Computacional** | Arduino + Python + MQTT / Colab | Simula a captura de dados de sensores (GPS, velocidade, temperatura, status da moto) e publica em tempo real. |
| **API Java** | Spring Boot + JPA + Oracle/PostgreSQL | Responsável pelo CRUD completo das entidades (Moto, Usuário, Filial, Agendamento, Evento) com cache, DTOs e validações. |
| **API .NET** | ASP.NET Core + Oracle EF Core | Oferece endpoints de integração e dashboard web com Razor Pages e Swagger. |
| **Mobile App** | React Native + Expo Router + Firebase Auth | Interface mobile para gestão e mapeamento das motos, com autenticação e i18n (pt/es). |
| **Banco de Dados** | Oracle Cloud / PostgreSQL (Railway) | Persistência unificada de dados da frota e logs de sensores. |
| **DevOps** | Docker + Azure CLI + Pipelines | Deploy automatizado da API e do banco em contêineres e VMs Linux (não root). |

---

## 🌐 Fluxo Completo de Dados

```mermaid
flowchart LR
    A[Sensores IoT / Simulação Colab] -->|Publica via MQTT/JSON| B[API Java Spring Boot]
    B -->|Persiste Dados| C[(Banco Oracle/PostgreSQL)]
    C --> D[API .NET Core / Dashboard]
    D --> E[App Mobile Expo + Firebase]
    D --> F[Dashboard Web (Gráficos e Mapas)]
```

---

## 📊 Funcionalidades Principais

- 🛰️ **Monitoramento de localização** e estado em tempo real das motos.  
- ⚙️ **Gestão de Filiais, Agendamentos, Usuários e Eventos.**  
- 🔔 **Alertas inteligentes** com base em status e métricas.  
- 💾 **Integração com banco relacional Oracle/PostgreSQL.**  
- 📱 **Aplicativo mobile multiplataforma** com login via Firebase Auth.  
- ☁️ **Containerização e Deploy na Nuvem (Azure / Railway).**  
- 🌍 **Internacionalização (pt / es)** e **modo claro/escuro**.  

---

## 🧠 Requisitos e Bibliotecas Principais

### 🐍 Ambiente de Simulação (Google Colab)

- Python 3.10+
- Bibliotecas:
  ```bash
  pip install pandas numpy matplotlib paho-mqtt requests
  ```
- Conexão com API: via `requests.post()` e `json.dumps()`  
- Leitura de sensores simulada via DataFrame e loops controlados  
- Geração de dashboards dinâmicos com gráficos (`matplotlib`, `plotly`)  

### ☕ API Java (MotoTrackAPI)
- Spring Boot 3.3.x
- Spring Data JPA
- Oracle / PostgreSQL Driver
- ModelMapper
- Swagger OpenAPI
- Flyway Migrations
- Cache com Redis
- Tratamento centralizado de exceções (`GlobalExceptionHandler`)

### ⚙️ API .NET
- ASP.NET Core 8
- Entity Framework Core
- Oracle.ManagedDataAccess
- Swagger UI
- Razor Pages / MVC

### 📱 Mobile (Expo)
- Expo SDK 52
- React Native 0.76
- Firebase Auth
- i18n (react-i18next)
- AsyncStorage
- Axios (API REST)

---

## 🚀 Execução no Google Colab

1. Acesse: [Google Colab](https://colab.research.google.com/)
2. Faça upload do arquivo: **`mototrack_sprint_4.ipynb`**
3. Execute célula por célula:
   - Instalação de dependências
   - Simulação dos sensores (IoT)
   - Envio de dados para API
   - Plotagem dos gráficos e dashboards
4. Verifique os resultados no painel final (métricas, mapas e logs).

---

## 🧰 Estrutura do Projeto

```
mototrack_sprint_4/
│
├── mototrack_sprint_4.ipynb     # Notebook principal (simulação e dashboard)
├── api-java/                    # API REST Spring Boot
├── api-dotnet/                  # API .NET Core
├── mobile/                      # App React Native (Expo)
├── database/                    # Scripts SQL (DDL, DML, PL/SQL)
├── docker/                      # Dockerfiles e compose.yml
└── README.md                    # Documentação principal
```

---

## 💻 Demonstração e Vídeo

🎬 **Vídeo demonstrativo (até 5 min):**
- Mostra o fluxo IoT → API → Banco → App / Dashboard.
- Demonstra integração em tempo real e comunicação entre módulos.

---

## 📚 Integração entre Disciplinas

| Disciplina | Contribuição |
|-------------|--------------|
| **IoT / Disruptive Architectures** | Captura e simulação de dados dos sensores. |
| **Java Advanced** | API REST com CRUD e integração com banco. |
| **.NET Advanced Business Development** | Dashboard e integração com Oracle via EF Core. |
| **Mobile Application Development** | App React Native com autenticação e i18n. |
| **Database Relational & Non-Relational** | Modelagem 3FN, scripts DDL/DML e consultas complexas. |
| **DevOps & Cloud Computing** | Dockerfile, Azure CLI, pipelines CI/CD. |

---

## 👥 Equipe e Créditos

| Nome | RM | Função |
|------|----|--------|
| Rafael Rodrigues de Almeida | **557837** | Desenvolvimento Full Stack, Integrações e Mobile |
| Lucas Kenji Miyahira | **555368** | DevOps, Azure e Deploy |
| Outros Integrantes | — | API, Banco, IoT e Dashboard |

---

## 🏁 Conclusão

O **MotoTrack Sprint 4** consolida o aprendizado multidisciplinar da FIAP, unindo tecnologias de **IoT, Java, .NET, Mobile, Cloud e Banco de Dados**.  
O resultado é uma **solução funcional, integrada e escalável**, demonstrando o domínio técnico e a capacidade de integração entre sistemas heterogêneos.

---

### 📎 Licença
Este projeto foi desenvolvido exclusivamente para fins acadêmicos (FIAP - Challenge Mottu 2025).
