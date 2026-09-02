# 🪙 Finn - Tutor Inteligente de Educação Financeira

O **Finn** é um assistente virtual e educador financeiro didático construído para auxiliar iniciantes a darem os primeiros passos no mundo dos investimentos. Executado de forma 100% local com o **Ollama** e integrado a uma interface conversacional em **Streamlit**, o agente ensina a "sopa de letrinhas" do mercado através de analogias do cotidiano, com segurança e sem promessas de ganhos milagrosos.

---

## 🎯 Funcionalidades do Finn

* **Tradução de Jargões Financeiros:** Desmistifica termos técnicos (CDI, CDB, Tesouro Selic, IPCA, FGC e Renda Variável) usando comparações didáticas e acessíveis do dia a dia.
* **Exemplos Baseados em Contexto Local:** Utiliza dados fictícios de fluxo financeiro, histórico de dúvidas e catálogo de investimentos para criar explicações contextualizadas à realidade do usuário.
* **Priorização da Reserva de Emergência:** Orienta o planejamento da base de segurança financeira e quitação de dívidas caras antes de sugerir qualquer exposição a riscos.
* **Guardrails Estritos de Segurança:**
  * **Natureza 100% Educativa:** Não faz consultoria ou recomendação explícita de compra e venda de ativos específicos (ações, cripto ou fundos).
  * **Sem Promessas de Rentabilidade:** Alerta contra riscos e nunca garante lucros na renda variável.
  * **Proteção de Privacidade:** Recusa solicitações de senhas, tokens bancários ou movimentações financeiras.
  * **Filtro Fora de Escopo:** Redireciona educadamente perguntas que fogem do ensino de finanças pessoais.
* **Respostas Concisas:** Estruturação obrigatória em até 3 parágrafos curtos, finalizando sempre com uma pergunta reflexiva para manter o aprendizado ativo.
* **Histórico de Conversa Persistente:** Interface interativa que preserva as mensagens enviadas e recebidas ao longo de toda a sessão de navegação.

---

## 📚 Alinhamento com o Conteúdo do Curso

O projeto consolida as competências práticas propostas no laboratório:

* **Modelos de Linguagem Locais (SLMs & LLMs):** Execução local via Ollama (`gpt-oss`), garantindo custo zero de API e privacidade total de dados.
* **Engenharia de Prompt:** Aplicação de system prompt com persona bem definida, diretrizes de conduta e exemplos *few-shot*.
* **Injeção de Contexto & RAG Básico:** Extração de dados tabulares e estruturados (CSV e JSON) diretamente para o prompt de inferência.
* **Desenvolvimento de Interfaces Web:** Criação de front-end com Streamlit gerenciando estado de sessão (`st.session_state`).

---

## 🏗️ Estrutura do Repositório

```text
├── assets/                  # Prints e evidências de execução da aplicação
├── data/                    # Bases locais para injeção de contexto
│   ├── historico_atendimento.csv
│   ├── perfil_investidor.json
│   ├── produtos_financeiros.json
│   └── transacoes.csv
├── docs/                    # Documentação técnica e relatórios do agente
│   ├── 01-documentacao-agente.md
│   ├── 02-base-conhecimento.md
│   ├── 03-prompts.md
│   ├── 04-metricas.md
│   └── 05-pitch.md
├── src/                     # Código-fonte principal
│   ├── app.py              # Interface Streamlit e integração com Ollama
│   └── README.md           # Guia de execução rápida
└── README.md                # Apresentação geral do projeto
```

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
