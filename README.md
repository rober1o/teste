# 🩺 Sistema Embarcado de Detecção de Diabetes com TinyML no RP2040

## 🔗 Links e Detalhes do Projeto

| Item | Status | Link |
| :--- | :--- | :--- |
| **Repositório GitHub** | Código-fonte | [https://github.com/TorRLD/diabetes-detection.git](https://github.com/TorRLD/diabetes-detection.git) |
| **Vídeo Demonstrativo** | Apresentação Técnica | [VideoApresentação-AprendizagemDeMaquina-Parte3.mp4](VideoApresentação-AprendizagemDeMaquina-Parte3.mp4) |
| **Data de Conclusão** | - | 09/12/2025 |
| **Polo** | - | Vitória da Conquista - BA |

---

## 🎯 Objetivo Geral

Desenvolver e validar um **dispositivo de auxílio diagnóstico** baseado em **Inteligência Artificial (TinyML)** na placa **BitDogLab**, capaz de inferir o risco de diabetes em tempo real. O sistema utiliza uma Rede Neural rodando localmente no microcontrolador **RP2040** e foi treinado com o dataset **Pima Indians Diabetes**.



---

## ⚙️ Descrição Funcional

O funcionamento do sistema é dividido em duas etapas principais: **Treinamento** (offline) e **Inferência** (no dispositivo).

### 1. Treinamento e Pré-processamento (Python)

* **Modelo:** A rede neural foi treinada em Python para classificar o risco com base em 8 variáveis clínicas (gravidez, glicose, pressão, pele, insulina, IMC, histórico e idade).
* **Preparação de Dados:** O código implementa uma lógica de **imputação de dados** (substituição de valores ausentes pela média) e **normalização MinMax rigorosa**.

### 2. Inferência na BitDogLab (Firmware RP2040)

* **Entrada de Dados:** O usuário insere os dados clínicos via Monitor Serial.
* **Execução da IA:** O firmware processa essas entradas e executa o modelo **TensorFlow Lite for Microcontrollers**.
* **Saída e Feedback:** O sistema retorna a probabilidade percentual da doença e classifica o resultado como **"Normal"** ou **"Risco Detectado"**.

---

## 💻 Como Clonar o Repositório

Para obter uma cópia local funcional para desenvolvimento e testes, siga os passos abaixo:

1.  **Pré-requisitos:** Certifique-se de ter o Git instalado em sua máquina.
2.  **Clonar:** Abra seu terminal ou prompt de comando e execute o seguinte comando:

```bash
git clone [https://github.com/TorRLD/diabetes-detection.git](https://github.com/TorRLD/diabetes-detection.git)
