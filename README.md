# Fluxi

### Sua IA privada no WhatsApp. Sem servidor externo. Sem mensalidade. 100% seu.

<div align="center">

![Dashboard](data/screenshot01.png)

</div>

---

## Por que Fluxi?

Você já quis ter um assistente de IA no WhatsApp, mas:

- Não quer pagar mensalidade de plataformas SaaS
- Não quer depender de servidores externos
- Não quer expor suas conversas para terceiros
- Quer controle total sobre o comportamento da IA

**Fluxi resolve tudo isso.**

Com Docker, um modelo de linguagem local (LM Studio, Ollama) e seu número de WhatsApp, você tem uma IA 100% privada funcionando em minutos.

---

## O que você pode fazer

**Conectar seu sistema financeiro**  
Lance compras, consulte saldos e gere relatórios direto pelo WhatsApp.

**Pesquisar na internet**  
Integre com Serper.dev, Brave Search ou outros e deixe a IA buscar informações para você.

**Perguntar sobre seus documentos**  
Adicione PDFs, manuais, contratos. A IA responde baseada no conteúdo deles.

**Ter múltiplos agentes no mesmo número**  
Crie um agente de vendas, outro de suporte, outro pessoal. Troque entre eles com `#01`, `#02`.

**Transcrever áudios automaticamente**  
Receba um áudio e a IA transcreve e responde (requer API Whisper).

**Ligar e desligar quando quiser**  
Comande `#desativar` para pausar, `#ativar` para voltar. Simples.

---

## Funcionalidades

| Recurso | Descrição |
|---------|-----------|
| **Múltiplos Agentes** | Crie agentes especializados e alterne entre eles |
| **RAG (Documentos)** | Adicione bases de conhecimento e faça perguntas |
| **Ferramentas Customizadas** | Conecte APIs com wizard visual, sem código |
| **MCP Protocol** | Integre ferramentas externas (GitHub, databases, etc) |
| **LLMs Locais** | Use Ollama, LM Studio ou llama.cpp - 100% offline |
| **LLMs na Nuvem** | OpenRouter, OpenAI, Anthropic, Google - sua escolha |
| **Comandos** | `#ativar`, `#desativar`, `#limpar`, `#status`, `#ajuda` |
| **Transcrição** | Converta áudios em texto automaticamente |
| **Métricas** | Acompanhe mensagens, tokens, tempo de resposta |
| **Dark Mode** | Interface clara ou escura |

---

## Screenshots

<div align="center">

| Dashboard | Sessão WhatsApp |
|-----------|-----------------|
| ![Dashboard](data/screenshot01.png) | ![Sessão](data/screenshot05.png) |

| Wizard de Ferramentas | Provedores LLM |
|-----------------------|----------------|
| ![Ferramentas](data/screenshot02.png) | ![LLM](data/screenshot03.png) |

| MCP Clients |
|-------------|
| ![MCP](data/screenshot04.png) |

</div>

---

## Como Começar

### Requisitos

- Docker instalado
- Um número de WhatsApp
- Um provedor LLM (local ou nuvem)

### 1. Clone e configure

```bash
git clone https://github.com/jjhoow/fluxi.git
cd fluxi
cp config.example.env .env
```

### 2. Inicie com Docker

```bash
docker-compose up -d --build
```

### 3. Acesse e conecte

1. Abra `http://localhost:8001`
2. Crie uma sessão WhatsApp
3. Escaneie o QR Code
4. Configure um provedor LLM
5. Crie seu primeiro agente

**Pronto.** Envie uma mensagem para o número conectado.

---

## Stack Técnica

| Camada | Tecnologia |
|--------|------------|
| **Backend** | Python, FastAPI, SQLAlchemy, Pydantic |
| **Frontend** | Jinja2, Bulma, HTMX |
| **Banco de Dados** | SQLite (padrão), PostgreSQL (produção) |
| **Vetorial** | ChromaDB |
| **WhatsApp** | Neonize (whatsmeow) |
| **LLM** | OpenRouter, OpenAI, Ollama, LM Studio |

---

## Arquitetura

```
fluxi/
├── agente/          # Sistema de agentes inteligentes
├── config/          # Configurações do sistema
├── ferramenta/      # Ferramentas customizadas (function calling)
├── llm_providers/   # Provedores LLM (local e nuvem)
├── mcp_client/      # Model Context Protocol
├── mensagem/        # Mensagens e histórico
├── metrica/         # Analytics e monitoramento
├── rag/             # Bases de conhecimento
├── sessao/          # Sessões WhatsApp
└── templates/       # Interface web
```

Cada módulo tem sua própria documentação em `[modulo]/README.md`.

---

## Changelog

### v0.2.0 - Novembro 2025

**Novos Recursos**
- Dark mode na interface
- Comandos personalizáveis por sessão (`#ativar`, `#desativar`)
- Tipos de mensagem configuráveis (ignorar, resposta fixa, etc)
- Suporte a mensagens multimodais (texto + imagem)

**Melhorias**
- Histórico de mensagens inclui respostas do assistente
- Sincronização automática de novos comandos
- Documentação atualizada de todos os módulos

**Correções**
- Comando `#desativar` não era reconhecido corretamente
- Histórico multimodal não era enviado ao LLM

### v0.1.0 - Outubro 2025

- Lançamento inicial
- Sistema de agentes com system prompts
- Ferramentas customizadas com wizard
- RAG com ChromaDB
- Integração MCP
- Múltiplos provedores LLM
- Interface web completa

---

## Contribuindo

Contribuições são bem-vindas!

1. Fork o projeto
2. Crie uma branch (`git checkout -b feature/nova-feature`)
3. Commit suas mudanças (`git commit -m 'Adiciona nova feature'`)
4. Push (`git push origin feature/nova-feature`)
5. Abra um Pull Request

---

## Comunidade

- [GitHub Issues](https://github.com/jjhoow/fluxi/issues) - Bugs e sugestões
- [GitHub Discussions](https://github.com/jjhoow/fluxi/discussions) - Dúvidas e ideias

---

## Dependências de Terceiros

Este projeto utiliza:

- **[neonize](https://github.com/krypton-byte/neonize)** - Cliente Python para WhatsApp Web
- **[whatsmeow](https://github.com/tulir/whatsmeow)** - Biblioteca Go para WhatsApp Web (via neonize)
- **[FastAPI](https://fastapi.tiangolo.com/)** - Framework web
- **[ChromaDB](https://www.trychroma.com/)** - Banco vetorial
- **[SQLAlchemy](https://www.sqlalchemy.org/)** - ORM

---

## Agradecimentos

- [FastAPI](https://fastapi.tiangolo.com/) pelo framework incrível
- [Neonize](https://github.com/krypton-byte/neonize) por tornar WhatsApp acessível em Python
- [ChromaDB](https://www.trychroma.com/) pelo banco vetorial simples e poderoso
- Comunidade open source por todas as bibliotecas que tornam isso possível

---

## Licença

Apache 2.0 - Veja [LICENSE](LICENSE) para detalhes.

---

<div align="center">

**Feito para quem quer controle total sobre sua IA.**

Se esse projeto te ajudou, deixa uma estrela!

</div>
