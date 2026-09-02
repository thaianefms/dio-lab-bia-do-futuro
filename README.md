# 🪙 Finn - Tutor Inteligente de Educação Financeira

Projeto desenvolvido como parte prática do laboratório da DIO focado na criação de agentes inteligentes locais, aplicando conceitos de engenharia de prompt, guardrails de segurança, injeção de contexto estruturado e interfaces conversacionais.

---

## 📚 Alinhamento com o Conteúdo do Curso

O projeto consolida as competências práticas trabalhadas ao longo das aulas em uma aplicação completa de ponta a ponta:

* **Modelos de Linguagem Locais (SLMs & LLMs):** Utilização do **Ollama** executando o modelo `gpt-oss` diretamente na máquina, explorando inferência local com privacidade de dados e sem custos de API por token.
* **Engenharia de Prompt e Definição de Persona:** Construção da identidade do assistente **Finn** com tom acolhedor e didático, uso de técnicas de *Few-Shot Prompting* e controle rigoroso de concisão (limitação em no máximo 3 parágrafos).
* **Injeção de Contexto & RAG Básico:** Extração e consolidação dinâmica de dados semiestruturados (arquivos JSON e CSV) para enriquecer as respostas do agente com histórico de compras, catálogo de investimentos e perfil de risco.
* **Guardrails e Alinhamento Ético:** Implementação de barreiras estritas para impedir recomendações explícitas de compra/venda de ativos, promessas de retornos milagrosos, exposição de dados sensíveis ou fuga de escopo temático.
* **Interface Web Conversacional:** Desenvolvimento de uma interface amigável com **Streamlit**, aplicando persistência de estado via `st.session_state` para manter o histórico de mensagens ativo na tela.

---

## 🏗️ Arquitetura e Estrutura do Repositório

```text
├── assets/                  # Prints, diagramas e evidências de execução
├── data/                    # Base de dados mockados para injeção de contexto
│   ├── historico_atendimento.csv
│   ├── perfil_investidor.json
│   ├── produtos_financeiros.json
│   └── transacoes.csv
├── docs/                    # Documentação técnica e relatórios de validação
│   ├── 01-documentacao-agente.md
│   ├── 02-base-conhecimento.md
│   ├── 03-prompts.md
│   ├── 04-metricas.md
│   └── 05-pitch.md
├── src/                     # Código-fonte da aplicação
│   ├── app.py              # Interface Streamlit e integração com o Ollama
│   └── README.md           # Guia rápido de execução do script
└── README.md                # Apresentação geral do projeto

---

## ⚙️ Tecnologias e Ferramentas

* **Linguagem:** Python 3.10+
* **Backend de IA:** Ollama (Modelo `gpt-oss`)
* **Interface de Usuário:** Streamlit
* **Manipulação de Dados:** Pandas e Módulo Nativo JSON
* **Comunicação HTTP:** Requests

---

## 🚀 Como Executar

### 1. Inicializar o Modelo no Ollama
Certifique-se de que o Ollama está instalado e com o modelo em execução:

```bash
ollama run gpt-oss
```

### 2. Instalar Dependências

Em um terminal com Python configurado, instale os pacotes necessários:

```bash
pip install streamlit pandas requests 
```

### 3. Rodar o Agente

Execute a aplicação a partir da raiz do projeto:

```bash
streamlit run .\src\app.py
```

O navegador abrirá automaticamente em `http://localhost:8501`.

---

## 🧪 Validação e Resultados

O agente foi submetido a uma bateria de testes funcionais descritos em `docs/04-metricas.md`, comprovando:

* **Aderência aos guardrails:** recusa amigável a recomendações diretas de compra ou promessas de lucros rápidos;
* **Didática adaptada:** foco em iniciantes por meio de analogias simples do cotidiano;
* **Uso consistente do contexto:** aproveitamento seguro dos dados dos clientes fictícios sem expor senhas ou informações confidenciais.