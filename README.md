# Academic AI Agents — RAG e Multi-Agent Systems

Este repositório apresenta **dois protótipos de agentes acadêmicos inteligentes** desenvolvidos com **Azure OpenAI, Microsoft Agent Framework e Python**.

Os notebooks demonstram **duas arquiteturas complementares de agentes de IA**:

1. **Agente acadêmico com RAG (Retrieval-Augmented Generation)** para revisão textual baseada em documentos.
2. **Sistema multiagente com tools externas e orquestração**, capaz de executar tarefas especializadas como revisão e indexação conceitual.

O objetivo é explorar o uso de **Large Language Models (LLMs)** para apoiar tarefas de **análise documentária, revisão acadêmica e organização do conhecimento**.

---

# Estrutura do Repositório

```

academic-ai-agents
│
├── agent_academico_rag.ipynb
├── agent_academico_tool.ipynb
│
├── indexacao.xlsx
│
└── README.md

```

O repositório contém **dois notebooks principais**, cada um demonstrando uma arquitetura distinta de agentes.

---

# Projeto 1 — agent_academico_rag

## Objetivo

Criar um **agente de revisão acadêmica baseado em RAG (Retrieval-Augmented Generation)** capaz de corrigir e melhorar textos utilizando um **documento de referência como contexto**.

O agente não responde apenas com base no modelo, mas também consulta um **documento base indexado semanticamente**.

## Como funciona

Pipeline do sistema:

```

PDF de referência
↓
Extração de texto
↓
Divisão em chunks
↓
Embeddings (Azure OpenAI)
↓
Busca semântica
↓
Contexto recuperado
↓
Agente de revisão acadêmica

```

## Capacidades do agente

O agente é capaz de:

- corrigir erros gramaticais
- melhorar clareza e coesão textual
- manter rigor acadêmico
- enriquecer o texto usando o contexto recuperado
- evitar geração de informações não presentes no documento

Esse modelo segue o padrão **RAG (Retrieval-Augmented Generation)**.

---

# Projeto 2 — agent_academico_tool

## Objetivo

Demonstrar uma **arquitetura multiagente baseada em ferramentas (tools)**.

Nesse sistema, diferentes agentes possuem papéis específicos e podem ser coordenados por um **orquestrador**.

## Arquitetura

```

Usuário
│
▼
Orquestrador
│
┌─┴─────────────┐
▼               ▼
Extrator      Revisor
(conceitos)   (texto)
│
▼
Tool Python
(salvar_indexacao_planilha)
│
▼
Planilha Excel

```

## Componentes

### Agente Extrator

Responsável por:

- extrair palavras-chave
- identificar conceitos principais
- identificar termos indexadores

Após a análise, o agente chama uma **tool Python** que salva a indexação em Excel.

---

### Agente Revisor

Responsável por:

- corrigir gramática
- melhorar clareza e coesão
- manter estilo acadêmico

---

### Orquestrador

O orquestrador decide **qual agente deve ser utilizado** com base na solicitação do usuário.

Exemplos:

| Solicitação | Agente usado |
|---|---|
| Revisar texto | Revisor |
| Extrair conceitos | Extrator |
| Indexação | Extrator |

Esse modelo demonstra **coordenação entre múltiplos agentes especializados**.

---

# Tecnologias Utilizadas

- Python
- Azure OpenAI
- Azure AI Foundry
- Microsoft Agent Framework
- Async/Await
- Embeddings
- Busca vetorial
- Retrieval-Augmented Generation (RAG)
- openpyxl

---

# Instalação

Clone o repositório:

```

git clone [https://github.com/SEU-USUARIO/academic-ai-agents.git](https://github.com/SEU-USUARIO/academic-ai-agents.git)

```

Entre na pasta:

```

cd academic-ai-agents

```

Crie o ambiente virtual:

```

python -m venv .venv

```

Ative o ambiente:

Windows

```

.venv\Scripts\activate

```

Linux / Mac

```

source .venv/bin/activate

```

Instale as dependências:

```

pip install openpyxl
pip install azure-ai-projects
pip install azure-identity
pip install python-dotenv

```

---

# Como Executar

Abra os notebooks:

```

agent_academico_rag.ipynb

```

ou

```

agent_academico_tool.ipynb

```

Execute as células sequencialmente.

---

# Objetivo Científico

Este projeto explora o uso de **agentes baseados em LLMs** para apoiar processos típicos da **organização do conhecimento**, incluindo:

- análise documentária
- extração terminológica
- indexação conceitual
- revisão acadêmica assistida por IA

---

# Possíveis Extensões

O sistema pode evoluir para:

- integração com **Azure AI Search**
- agentes com **memória persistente**
- revisão acadêmica multi-etapas
- geração automática de **vocabulários SKOS**
- integração com **ontologias OWL**
- aplicações multimodais para **texto, imagem e vídeo**

---

# Autoria

**Denise Cavalcante**

Pesquisa em:

- Organização do Conhecimento
- Ontologias
- Anotação Semântica
- Inteligência Artificial aplicada à indexação

---

# Licença

Projeto experimental para fins educacionais e de pesquisa.
```


