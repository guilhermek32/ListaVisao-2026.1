# Lista 04 - Visao Computacional

Este projeto contem as solucoes da Lista 04 usando:

- Questao 1(a): HOG com OpenCV + SVM para classificacao Cat vs Dog.
- Questao 1(b): CNNs com transfer learning usando VGG16, ResNet50 e MobileNetV2.
- Questao 2: deteccao e contagem de veiculos em video usando YOLOv8.

## Estrutura Esperada

Execute os notebooks a partir da pasta raiz do projeto:

```text
Lista 04/
├── README.md
├── lista4.pdf
├── bridge.mp4
├── PetImages/
│   ├── Cat/
│   └── Dog/
├── outputs/
├── q1_partA_hog_svm.ipynb
├── q1_partB_transfer_learning.ipynb
└── q2_partA_partB.ipynb
```

## Dataset da Questao 1

Dataset usado: Dog and Cat Classification Dataset

Link Kaggle:

```text
https://www.kaggle.com/datasets/bhavikjikadara/dog-and-cat-classification-dataset/data
```

Baixe o dataset pelo navegador no link acima. Depois extraia o arquivo `.zip` e coloque as pastas `Cat` e `Dog` dentro de `PetImages/`.

A estrutura final obrigatoria e:

```text
PetImages/
├── Cat/
│   ├── 0.jpg
│   ├── 1.jpg
│   └── ...
└── Dog/
    ├── 0.jpg
    ├── 1.jpg
    └── ...
```

Se o arquivo extraido vier com uma pasta intermediaria, mova apenas `Cat/` e `Dog/` para dentro de `PetImages/`.

Opcional via Kaggle CLI:

```bash
mkdir -p PetImages
kaggle datasets download -d bhavikjikadara/dog-and-cat-classification-dataset
unzip dog-and-cat-classification-dataset.zip -d PetImages
```

Depois confira se existe:

```bash
ls PetImages/Cat PetImages/Dog
```

## Ambiente Python

Este projeto usa `uv` para criar ambientes e instalar dependencias.

### Questao 1(a) - HOG + SVM

Crie ou use ambiente local:

```bash
uv venv .venv
uv pip install opencv-python scikit-learn numpy pandas matplotlib tqdm ipykernel
```

Abra o notebook:

```text
q1_partA_hog_svm.ipynb
```

Execute as celulas em ordem.

Saidas principais:

```text
outputs/partA/
```

ou, na versao organizada do repositorio:

```text
outputs/q1partA/
```

## Questao 1(b) - Transfer Learning

TensorFlow pode nao instalar em Python 3.14. Use Python 3.13 ou 3.12.

Ambiente recomendado:

```bash
uv venv .venv-tf --python 3.13
uv pip install --python .venv-tf/bin/python tensorflow opencv-python scikit-learn pandas matplotlib tqdm ipykernel
```

Abra o notebook com o kernel/interpreter de `.venv-tf`:

```text
q1_partB_transfer_learning.ipynb
```

Execute as celulas em ordem. A primeira execucao baixa pesos ImageNet para VGG16, ResNet50 e MobileNetV2.

Saidas principais:

```text
outputs/partB/
```

ou, na versao organizada do repositorio:

```text
outputs/q1partB/
```

## Questao 2 - YOLOv8

Instale dependencias:

```bash
uv pip install ultralytics opencv-python matplotlib
```

Arquivo de entrada esperado na raiz:

```text
bridge.mp4
```

Abra o notebook:

```text
q2_partA_partB.ipynb
```

Execute as celulas em ordem. O modelo `yolov8n.pt` sera baixado automaticamente pela biblioteca Ultralytics se ainda nao existir.

Saidas esperadas:

```text
outputs/q2partA/Q2A_bridge_detected.avi
outputs/q2partB/Q2B_vehicle_count_graph.png
```
