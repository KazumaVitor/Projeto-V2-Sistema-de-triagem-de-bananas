# 🍌 Projeto V2 - Sistema de Triagem de Bananas

Interface web para análise automática de imagens de bananas, com resultados em tempo real e métricas de confiança.

---

## 📖 Descrição

Sistema de **Visão Computacional** baseado em **YOLO** para classificação automática do estágio de maturação de bananas.  
Aplicação prática para reduzir desperdício na agroindústria e otimizar logística de distribuição.

---

## 👥 Integrantes

- Ronald Roland Filho  
- Victor José Moraes de Lima  
- Vítor Tetsuya Kazuma  

---

## 🎯 Tema do Projeto

Triagem automática de bananas por maturação utilizando **YOLO Classification (YOLO11n-cls)**.

---

## 🤖 Modelo Base Utilizado

- **YOLO11n-cls (Ultralytics)**

**Justificativa:** modelo leve, rápido e eficiente para classificação de imagens, permitindo execução em tempo real com baixo custo computacional.

---

## 📊 Dataset

- **Origem:** Banana Ripeness Classification Dataset (Kaggle)  
- **Número de imagens:** 11.793  
- **Classes:**  
  - Unripe (Verde)  
  - Ripe (Madura)  
  - Overripe (Muito madura)  
  - Rotten (Estragada)  

Dataset já previamente rotulado (não foi necessária anotação manual).

---

## 📈 Resultados do Treinamento

-Top-1 Accuracy: 99,11%

-Top-5 Accuracy: 100%

-Loss final (val): ~0.05

## 📈 Resultados do Treinamento

### Evolução de Loss e Accuracy
![Resultados do Treinamento](prints/results.png)

### Matriz de Confusão
![Matriz de Confusão](prints/confusion_matrix.png)

---

## 🏗️ Arquitetura da Aplicação

```text
┌──────────────┐
│   Usuário    │
└──────┬───────┘
       ↓
┌──────────────────────┐
│  Interface Web (UI)  │
└─────────┬────────────┘
          ↓
┌──────────────────────┐
│   API FastAPI        │
└─────────┬────────────┘
          ↓
┌──────────────────────┐
│  YOLO11n-cls Model   │
└──────────────────────┘




     🌐 Endpoints da API
GET /
Verifica se a API está ativa
Resposta:

json
{
  "mensagem": "API de Classificação de Bananas ativa"
}
POST /predict
Classifica a imagem enviada
Entrada: imagem (jpg, png, jpeg)
Saída:

json
{
  "classe": "ripe",
  "confianca": 97.0
}

🛠️ Tecnologias Utilizadas

*Python

*Ultralytics YOLO

*FastAPI

*OpenCV

*NumPy

*Pillow

*HTML, CSS, JavaScript

*Google Colab

📦 Pesos do Modelo

Arquivo local: models/best.pt

Link alternativo: Google Drive(https://drive.google.com/drive/my-drive?hl=pt-br)

🚀 Como Executar o Projeto
bash
# Criar ambiente virtual
python -m venv venv
source venv/bin/activate   # Linux/Mac
venv\Scripts\activate      # Windows

# Instalar dependências
pip install -r requirements.txt

# Executar servidor
uvicorn backend.main:app --reload

Acesse a documentação interativa em:
👉 http://127.0.0.1:8000/docs  
👉 http://127.0.0.1:8000/redoc
