# [cite_start]🩺 Sistema Embarcado de Detecção de Diabetes com TinyML no RP2040 [cite: 10]

---

## 🔗 Link Demonstrativo

| Item | Link |
| :--- | :--- |
| **Vídeo Demonstrativo** | [cite_start][VideoApresentação-AprendizagemDeMaquina-Parte3.mp4] [cite: 7] |

---

## 🎯 Objetivo Geral

[cite_start]Desenvolver e validar um dispositivo de auxílio diagnóstico baseado em Inteligência Artificial (TinyML) na placa BitDogLab, capaz de inferir o risco de diabetes em tempo real através de uma Rede Neural, rodando localmente no microcontrolador RP2040, utilizando o dataset Pima Indians Diabetes[cite: 12].


---

## [cite_start]⚙️ Descrição Funcional [cite: 13, 14]

O funcionamento do sistema é dividido em treinamento e inferência:

### 1. Treinamento e Pré-processamento (Python)

* [cite_start]**Modelo:** O modelo foi treinado em Python para classificar o risco com base em 8 variáveis clínicas (gravidez, glicose, pressão, pele, insulina, IMC, histórico e idade)[cite: 15].
* [cite_start]**Preparação de Dados:** O código implementa uma lógica de imputação de dados (substituição de valores ausentes pela média) e normalização MinMax rigorosa[cite: 16].

### 2. Inferência na BitDogLab (Firmware RP2040)

* [cite_start]**Entrada de Dados:** O usuário insere os dados clínicos via Monitor Serial[cite: 17].
* [cite_start]**Execução da IA:** O firmware processa essas entradas e executa o modelo TensorFlow Lite for Microcontrollers[cite: 18].
* [cite_start]**Saída e Feedback:** O sistema retorna a probabilidade percentual da doença e classifica o resultado como "Normal" ou "Risco Detectado"[cite: 19].

---

## 💻 Como Clonar e Configurar

### 1. Clonar o Repositório

Para obter o código-fonte, utilize o comando `git clone` e acesse o diretório do projeto:

```bash
git clone [https://github.com/TorRLD/diabetes-detection.git](https://github.com/TorRLD/diabetes-detection.git) 
cd diabetes-detection
