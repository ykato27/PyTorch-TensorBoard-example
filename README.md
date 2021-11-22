# PyTorch-TensorBoard-example

PyTorch の学習 : TensorBoard でモデル、データと訓練を可視化

## リポジトリ構成

```
.
├── README.md
├── data
├── docker
│   ├── Dockerfile
│   └── requirements.txt
├── docker-compose-loacl.yml
├── docs
├── models
├── notebooks
│   ├── PyTorch-TensorBoard_example.ipynb
│   ├── data
│   │   └── FashionMNIST
│   │       └── raw
│   │           ├── t10k-images-idx3-ubyte
│   │           ├── t10k-images-idx3-ubyte.gz
│   │           ├── t10k-labels-idx1-ubyte
│   │           ├── t10k-labels-idx1-ubyte.gz
│   │           ├── train-images-idx3-ubyte
│   │           ├── train-images-idx3-ubyte.gz
│   │           ├── train-labels-idx1-ubyte
│   │           └── train-labels-idx1-ubyte.gz
│   └── runs
│       └── fashion_mnist_experiment_1
│           ├── 00000
│           │   └── default
│           │       ├── metadata.tsv
│           │       ├── sprite.png
│           │       └── tensors.tsv
│           ├── events.out.tfevents.1637582485.1660a54c475f.56.0
│           ├── events.out.tfevents.1637583273.1660a54c475f.56.1
│           ├── events.out.tfevents.1637583483.1660a54c475f.56.2
│           ├── events.out.tfevents.1637583965.1660a54c475f.56.10
│           ├── events.out.tfevents.1637583965.1660a54c475f.56.11
│           ├── events.out.tfevents.1637583965.1660a54c475f.56.3
│           ├── events.out.tfevents.1637583965.1660a54c475f.56.4
│           ├── events.out.tfevents.1637583965.1660a54c475f.56.5
│           ├── events.out.tfevents.1637583965.1660a54c475f.56.6
│           ├── events.out.tfevents.1637583965.1660a54c475f.56.7
│           ├── events.out.tfevents.1637583965.1660a54c475f.56.8
│           ├── events.out.tfevents.1637583965.1660a54c475f.56.9
│           └── projector_config.pbtxt
├── pyproject.toml
├── setup.cfg
├── src
│   └── __init__.py
├── tests
│   └── __init__.py
└── work
```

## 環境詳細

- Python : 3.9.6

## 事前準備

- Docker インストール

## 環境構築

- dockerのbuild(Dockerfileやrequirements.txtを変えた場合に実行)

```
docker-compose -f docker-compose-{*構築対象}.yml build
```

- dockerコンテナ起動 # デーモン起動

```
docker-compose -f docker-compose-{*構築対象}.yml up -d
```

- 起動中のdockerコンテナ確認

```
docker ps
```

- dockerコンテナに入る

```
docker exec -it {*構築対象} bash
```

- dockerコンテナ内でjupyter labの起動

    ```
    jupyter lab --allow-root --ip=0.0.0.0 --port 8888 --no-browser --NotebookApp.token=''
    ```

    - ブラウザからアクセス http://127.0.0.1:8888/

- dockerコンテナ内でtensorboadの起動例

    ```
    tensorboard --logdir="/home/work/[任意のディレクトリ名]" --host 0.0.0.0 --port 6006
    ```

    - ブラウザからアクセス http://127.0.0.1:6006

## 動作環境

マシンスペック（Mac)

- MacBook Air (Retina, 13-inch, 2018)
- 1.6 GHz デュアルコアIntel Core i5
- 8 GB 2133 MHz LPDDR3
