# Visão Computacional: classificação e detecção (UFAL 2026.1)

Soluções da disciplina de Visão Computacional da UFAL. O projeto compara uma abordagem clássica com deep learning na classificação de imagens e usa YOLOv8 para detectar e contar veículos em vídeo.

## 📊 Resultados: gato × cachorro (≈25 mil imagens, teste com 7.498)

| Modelo | Abordagem | Acurácia | F1 macro |
|---|---|---|---|
| **ResNet50** | Transfer learning (ImageNet) | **98,9%** | **0,989** |
| MobileNetV2 | Transfer learning (ImageNet) | 98,5% | 0,985 |
| VGG16 | Transfer learning (ImageNet) | 97,7% | 0,977 |
| HOG + SVM linear | Features clássicas (OpenCV) + ajuste de `C` | 75,3% | 0,753 |

Com transfer learning, o erro caiu de cerca de 25% (baseline clássico) para cerca de 1%. As matrizes de confusão, curvas de treino e exemplos de predição estão em [`Lista_04/outputs/`](Lista_04/outputs).

## 🚗 Detecção e contagem de veículos com YOLOv8

- Detecção de veículos quadro a quadro em vídeo de uma ponte, usando `yolov8n` (Ultralytics).
- Contagem de veículos ao longo do tempo, com gráfico gerado automaticamente (`outputs/q2partB/Q2B_vehicle_count_graph.png`).

## 📁 Estrutura

```text
Lista_04/
├── q1_partA_hog_svm.ipynb            # HOG + SVM (baseline clássico)
├── q1_partB_transfer_learning.ipynb  # VGG16, ResNet50, MobileNetV2
├── q2_partA_partB.ipynb              # YOLOv8: detecção e contagem
└── outputs/                          # métricas, gráficos e vídeos gerados
```

## ▶️ Como executar

As instruções completas (dataset do Kaggle, ambientes com `uv` e dependências) estão em [`Lista_04/README.md`](Lista_04/README.md).

## 🧰 Stack

`TensorFlow/Keras` · `OpenCV` · `scikit-learn` · `Ultralytics YOLOv8` · `pandas` · `matplotlib`

---
Autor: **Antonio Guilherme da Silva**, Ciência da Computação, UFAL
