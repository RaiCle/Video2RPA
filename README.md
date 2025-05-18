# 🤖 Video2RPA Bot Generator 🚀

Transforme demonstrações em vídeo de processos web em bots RPA Python/Selenium robustos e configuráveis, impulsionado por Inteligência Artificial!

[![Python Version](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT) ---

## 📜 Sumário

* [Visão Geral](#-visão-geral)
* [⚠️ Nota Importante para Usuários](#️-nota-importante-para-usuários)
* [✨ Funcionalidades Principais](#-funcionalidades-principais)
* [🛠️ Tecnologias Utilizadas](#️-tecnologias-utilizadas)
* [⚙️ Como Funciona (Fluxo de Trabalho)](#️-como-funciona-fluxo-de-trabalho)
* [🚀 Começando](#-começando)
    * [Pré-requisitos](#pré-requisitos)
    * [Instalação](#instalação)
    * [Configuração](#configuração)
    * [Execução](#execução)
      
---

## 🎯 Visão Geral

Este projeto visa simplificar e acelerar o desenvolvimento de bots de Automação Robótica de Processos (RPA) para tarefas web. Através da análise de gravações de tela (vídeos) que demonstram um processo manual, este sistema utiliza modelos de linguagem avançados (Google Gemini) para gerar automaticamente o código Python (utilizando Selenium) necessário para automatizar essas tarefas. O resultado é um bot RPA funcional, com código comentado, tratamento de erros e configuração externalizada.

A ideia é oferecer um **ponto de partida robusto**, economizando tempo na fase inicial de desenvolvimento de um bot RPA.

---

## ⚠️ Nota Importante para Usuários

* **Necessidade de Revisão Técnica:** Este projeto gera um código base ou um protótipo. **É esperado que o usuário tenha conhecimentos de desenvolvimento em Python e Selenium, ou que envie o código gerado para um desenvolvedor experiente para revisão, ajustes e finalização.** A IA pode não interpretar perfeitamente todas as nuances do vídeo ou gerar código 100% otimizado ou livre de erros para todos os cenários.
* **Interpretação de Vídeo:** Se o agente de IA não conseguir interpretar completamente o vídeo (devido à complexidade, baixa qualidade, ou limitações do modelo utilizado), ele tentará gerar um **esqueleto de projeto ou um código base** com as partes que conseguiu entender. Este esqueleto ainda exigirá trabalho de um desenvolvedor para se tornar um bot completo e funcional.
* **Foco da Ferramenta:** Considere esta ferramenta como um assistente para acelerar o desenvolvimento, não como uma solução final "plug-and-play" para todos os casos.

---

## ✨ Funcionalidades Principais

* **Análise Inteligente de Vídeo:** Interpreta as ações visuais de um vídeo para entender passos de automação.
* **Geração Automática de Código Python:** Cria scripts Python com Selenium WebDriver.
* **Criação de Seletores (XPaths):** Tenta identificar e gerar XPaths para elementos web.
* **Configuração Externalizada:** Gera um arquivo `params.json` para URLs, credenciais (placeholders), etc.
* **Código Orientado a Objetos:** Estrutura o bot gerado dentro de uma classe Python.
* **Documentação no Código:** Adiciona comentários explicativos no código.
* **Tratamento de Erros:** Incorpora blocos `try-except` básicos.
* **Revisão por IA (Opcional):** Um segundo agente de IA pode revisar o código gerado.

---

## 🛠️ Tecnologias Utilizadas

* **Linguagem Principal:** Python (3.8+)
* **Inteligência Artificial:** Google Gemini (via API `google-generativeai` e `google.adk`)
    * **Modelo Principal (para geração complexa):** Idealmente `gemini-2.5-pro-preview`.
    * **Modelo Secundário (para tarefas mais simples ou como fallback):** `gemini-2.0-flash`.
* **Automação Web:** Selenium WebDriver
* **Navegador Alvo:** Google Chrome
* **Gerenciamento de WebDriver:** Webdriver Manager
* **Manipulação de Arquivos/JSON:** `os`, `json`

---

## ⚙️ Como Funciona (Fluxo de Trabalho)

1.  **Entrada:** Usuário fornece um vídeo do processo web.
2.  **Análise (IA):** Agente "Analisador de Vídeo" (Gemini) interpreta as ações.
3.  **Geração (IA):** Código Python (Selenium) e `params.json` são criados.
4.  **Revisão (IA Opcional):** Agente "Revisor de Código" (Gemini) refina o script.
5.  **Saída:** Usuário recebe um bot RPA base, que provavelmente necessitará de ajustes por um desenvolvedor.

---

## 🚀 Começando

### Pré-requisitos

* Python 3.8 ou superior.
* `pip` instalado.
* Google Chrome instalado.
* Uma **API Key do Google Gemini**.
* Um **Projeto Google Cloud com FATURAMENTO ATIVO** para usar os modelos Gemini Pro/Preview.

### Instalação

1.  **Clone o repositório:**
    ```bash
    git clone [https://github.com/RaiCle/Video2RPA.git](https://github.com/RaiCle/Video2RPA.git)
    ```
2.  **Crie e ative um ambiente virtual (recomendado):**
    ```bash
    O projeto foi feito no Google Colab, use o mesmo ou algum de sua preferencia.
    ```
3.  **Instale as dependências**:
    ```txt
    google-generativeai
    google-genai
    google-ai-generativelanguage # Pode ser necessário para algumas funcionalidades do ADK
    google-cloud-aiplatform # Se usar Vertex AI
    # Verifique os imports exatos do 'google.adk' para listar as dependências corretas.
    # Exemplo, se ADK for um pacote separado: google-adk
    selenium
    webdriver-manager
    ```

### Configuração

1.  **API Key do Google Gemini:** Configure sua `GOOGLE_API_KEY` como uma variável de ambiente.
2.  **Faturamento Google Cloud:** Certifique-se de que o projeto Google Cloud associado à sua API Key tenha o faturamento ativo. Consulte a seção [Sobre os Modelos Gemini Utilizados](#-sobre-os-modelos-gemini-utilizados).
