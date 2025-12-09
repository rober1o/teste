# 🩺 Sistema Embarcado de Detecção de Diabetes com TinyML no RP2040

## 🔗 Links e Detalhes do Projeto

| Item | Status | Link |
| :--- | :--- | :--- |
| **Repositório GitHub** | Código-fonte | [cite_start][https://github.com/TorRLD/diabetes-detection.git](https://github.com/TorRLD/diabetes-detection.git) [cite: 5] |
| **Vídeo Demonstrativo** | Apresentação Técnica | [cite_start][VideoApresentação-AprendizagemDeMaquina-Parte3.mp4](VideoApresentação-AprendizagemDeMaquina-Parte3.mp4) [cite: 7] |
| **Data de Conclusão** | - | [cite_start]09/12/2025 [cite: 3] |
| **Polo** | - | [cite_start]Vitória da Conquista - BA [cite: 1] |

---

## 🎯 Objetivo Geral

[cite_start]Desenvolver e validar um **dispositivo de auxílio diagnóstico** baseado em **Inteligência Artificial (TinyML)** na placa **BitDogLab** [cite: 12][cite_start], capaz de inferir o risco de diabetes em tempo real[cite: 12]. [cite_start]O sistema utiliza uma Rede Neural rodando localmente no microcontrolador **RP2040** [cite: 12] [cite_start]e foi treinado com o dataset **Pima Indians Diabetes**[cite: 12].



---

## ⚙️ Descrição Funcional

[cite_start]O funcionamento do sistema é dividido em duas etapas principais: **Treinamento** (offline) e **Inferência** (no dispositivo)[cite: 14].

### 1. Treinamento e Pré-processamento (Python)

* [cite_start]**Modelo:** A rede neural foi treinada em Python para classificar o risco com base em 8 variáveis clínicas (gravidez, glicose, pressão, pele, insulina, IMC, histórico e idade)[cite: 15].
* [cite_start]**Preparação de Dados:** O código implementa uma lógica de **imputação de dados** (substituição de valores ausentes pela média) e **normalização MinMax rigorosa**[cite: 16]. [cite_start]Este passo é crucial para garantir que os dados de entrada estejam na escala exata esperada pela rede neural implantada[cite: 16].

### 2. Inferência na BitDogLab (Firmware RP2040)

* [cite_start]**Entrada de Dados:** O usuário insere os dados clínicos via Monitor Serial[cite: 17].
* [cite_start]**Processamento:** O firmware processa essas entradas, executa o modelo **TensorFlow Lite for Microcontrollers** [cite: 18] [cite_start]e retorna a probabilidade percentual da doença[cite: 18].
* [cite_start]**Saída e Feedback:** O sistema classifica o resultado como **"Normal"** ou **"Risco Detectado"** com base na probabilidade calculada, informando um percentual[cite: 19].

---

## 💡 Pontos Relevantes e Otimização

[cite_start]O projeto foca na eficiência e robustez para garantir o funcionamento em ambientes de recursos limitados como o RP2040[cite: 20]:

* [cite_start]**Eficiência do Código:** Utilização de `MicroMutableOpResolver` para otimizar o uso de memória RAM/Flash do RP2040, carregando apenas as operações matemáticas essenciais (`FullyConnected`, `Relu`, `Softmax`)[cite: 26].
* [cite_start]**Robustez:** Implementação de tratamento de entrada para garantir que dados "crus" (ex: glicose 120 mg/dL) sejam convertidos corretamente para o formato flutuante normalizado que a IA compreende[cite: 27].
* **Validação em Tempo Real (Demonstrada):**
    * [cite_start]**Caso Negativo (Normal):** Testado com dados de um paciente saudável (Glicose 80, IMC 22, Idade 22)[cite: 22]. [cite_start]O modelo retornou **0.29% de chance de diabetes**[cite: 23].
    * [cite_start]**Caso Positivo (Alto Risco):** Testado com dados críticos (Glicose 189, Insulina 846, Idade 59)[cite: 24]. [cite_start]O modelo retornou **85.25% de chance**, alertando corretamente o risco[cite: 25].

---

## 🧑‍🤝‍🧑 Equipe

| Nome | |
| :--- | :--- |
| **Heitor Lemos** | [cite_start]Membro da Equipe [cite: 2] |
| **Luiz Filipe Ribeiro** | [cite_start]Membro da Equipe [cite: 2] |
| **Roberto Cardoso** | [cite_start]Membro da Equipe [cite: 2] |
| **Paulo César Di Lauro** | [cite_start]Membro da Equipe [cite: 2] |
