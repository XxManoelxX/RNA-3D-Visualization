# 🧬 Stanford RNA 3D Folding - Kaggle Competition

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Python](https://img.shields.io/badge/python-3.10%2B-blue.svg)](https://www.python.org/)
[![Kaggle](https://img.shields.io/badge/Kaggle-Competition-blue)](https://www.kaggle.com/competitions/stanford-rna-3d-folding)

Este repositório contém a pipeline desenvolvida para a competição [Stanford RNA 3D Folding](https://www.kaggle.com/competitions/stanford-rna-3d-folding) no Kaggle. O objetivo é prever estruturas 3D de moléculas de RNA com base em múltiplos alinhamentos de sequência (MSA).

---

## 🔍 Visão Geral

A estrutura do RNA determina suas funções biológicas, e prever sua forma tridimensional é um desafio essencial em biologia computacional. Este projeto aborda o problema utilizando:

- 📊 **Inferência de contatos** com base em MSA.
- 🧱 **Reconstrução de estrutura 3D** baseada nos contatos previstos.
- 🧪 **Avaliação quantitativa** por TM-score e alinhamento estrutural.
- 🧬 **Visualização interativa** com Py3Dmol.

---

## 🗂️ Estrutura do Projeto

├── notebooks/
│ └── RNA_3D_Visualization_Value_MSA_com_avaliacao.ipynb
├── src/
│ ├── contact_inference.py
│ ├── structure_builder.py
│ ├── visualization.py
│ └── evaluation.py
├── data/
│ ├── msa/ # Arquivos de múltiplos alinhamentos
│ └── predictions/ # Coordenadas previstas
├── results/
│ └── tm_scores.csv # Avaliações TM-score
├── environment.yml
└── README.md


---
📈 Resultados
As estruturas geradas foram avaliadas por TM-score comparando com estruturas de referência. A pipeline foi projetada para ser modular, permitindo testes com diferentes estratégias de inferência e geração 3D.


