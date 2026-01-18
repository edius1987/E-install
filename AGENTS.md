# AGENTS.md - Diretrizes para Agentes de IA (E-install)
```
# Criado em qui jan 15 23:29:20 2025

# @autor: edius

# email: ediusferreira@gmail.com

# licença: MIT
------

## name: "E-install" description: "Gerador de instalador de aplicativos TUI (Terminal User Interface) baseado em Python, utilizando Textual e Rich, gerenciado via uv." category: "DevOps / Automation" author: "edius" authorUrl: "https://github.com/edius1987/E-install" tags: ["python", "textual", "rich", "uv", "installer-generator"] lastUpdated: "2025-01-15"
```
## 🎯 Objetivo do Projeto

Transformar a lógica de aplicações web TypeScript em um gerador de instaladores nativos em Python. O foco principal é a **utilidade real** e a **usabilidade superior** através de interfaces de terminal modernas.

## 🛠 Stack Tecnológica

- 

  **Linguagem**: Python 3.14+ (Padrão) 1

  

  

- 

  **Interface TUI**: Textual & Rich 2

  

  

- 

  **Gestão de Projeto**: `uv` 3

  

  

- 

  **Qualidade/Linting**: Ruff 4

  

  

- **Saída Final**: Script Bash `e_install.sh` com cabeçalho padronizado.

------

## 🤖 Regras de Ouro para o Agente

### 1. Mentalidade e Fluxo

- **Pense como um Engenheiro Sênior**: Não tome decisões baseadas em suposições; avalie pelo menos duas opções antes de codificar.

- 

  **Ciclo de Desenvolvimento**: Definição do problema → Mudança pequena e segura → Revisão → Refatoração → Repetição. 5

  

  

- **Leitura Total**: Antes de alterar qualquer arquivo, leia-o de ponta a ponta para entender o contexto completo, referências e dependências.

### 2. Padrões de Código (Python)

- **Simplicidade**: Siga o estilo de codificação Standard. 

- **Limites de Arquivo**: Máximo de 300 linhas por arquivo (LOC).

- **Limites de Função**: Máximo de 50 linhas por função e no máximo 5 parâmetros.

- **Complexidade**: Complexidade ciclomática deve ser $\le 10$. Caso exceda, refatore imediatamente.

### 3. Estrutura do Projeto (Padrão `uv`)

Plaintext

```
E-install/
├── src/
│   ├── e_install/
│   │   ├── tui/          # Componentes Textual/Rich
│   │   ├── core/         # Lógica de geração do .sh
│   │   └── utils/        # Helpers e validadores
├── tests/                # Testes com Pytest/Ruff
├── CODE_OF_CONDUCT.md    # código de conduta
├── LINCESE				  # linceça
├── README.md			  # Readme
├── INSTALL.md			  # orintações para instalação
├── pyproject.toml        # Configuração uv
└── AGENTS.md             # Este guia
```

------

## 🚀 Guia de Implementação de Funcionalidades

### Geração do `e_install.sh`

Todo arquivo gerado deve obrigatoriamente conter o cabeçalho:

Bash

```
# ═══════════════════════════════════════════════════════════════════════════════
# E-install
# Github https://github.com/edius1987/E-install
# ═══════════════════════════════════════════════════════════════════════════════
# @autor: ediusferreira
# email: ediusferreira@gmail.com
# licença: MIT
# ═══════════════════════════════════════════════════════════════════════════════
```

### Segurança e Tratamento de Erros

- **Zero Secrets**: Nunca cometa chaves ou credenciais no código ou logs.

- **Validação Estrita**: Normalize e valide todos os inputs vindos da interface TUI antes de processar a geração do script.

- **Exceções Específicas**: Capture apenas erros conhecidos e forneça mensagens claras para o usuário final na interface Rich. 

  

  

------

## 🧪 Estratégia de Testes e Qualidade

- **Ruff**: Utilize o `ruff` para linting e formatação automática antes de cada commit. 

- **Testes Determinísticos**: Novos recursos exigem novos testes. Correções de bugs exigem testes de regressão que falham sem a correção.

- **Caminhos**: Sempre inclua um teste de "caminho feliz" (sucesso) e um de "falha crítica".

------

## 📝 Registro de Alterações (Changelog)

### v0.1.0 (2025-01-15)

- Definição da arquitetura base (Python + Textual + uv).
- Criação do guia de agentes para padronização do desenvolvimento.

