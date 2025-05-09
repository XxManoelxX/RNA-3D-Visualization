# 🧬 RNA 3D Folding - Kaggle Competition

Este repositório contém a solução desenvolvida para a competição [Stanford RNA 3D Folding](https://www.kaggle.com/competitions/stanford-rna-3d-folding), hospedada no Kaggle. O desafio consiste em prever as **estruturas tridimensionais** de moléculas de RNA com base em informações de sequência e **alinhamento múltiplo de sequências (MSA)**.

---

## 🎯 Objetivo

Prever a **estrutura 3D de cadeias de RNA** utilizando dados derivados de **MSA (Multiple Sequence Alignment)**, que refletem informações evolutivas e estruturais compartilhadas entre moléculas homólogas. O modelo ideal deve estimar com precisão as coordenadas espaciais dos átomos de carbono (C4') em cada nucleotídeo.

---

## 📦 Dados

A competição fornece os seguintes tipos de dados:

### 🧬 Dados de Entrada (Input)
- `sequence`: sequência de nucleotídeos (A, U, G, C).
- `msa` (Multiple Sequence Alignment): alinhamento de sequências relacionadas.
- `seq_id`: identificador único da sequência.
- `sequence_order`: ordem da cadeia no MSA.
- `seq_length`: número de nucleotídeos.

### 📌 Dados de Treinamento
- Arquivos `.npy` contendo as coordenadas reais (`real_structure.npy`) dos átomos C4' para milhares de cadeias de RNA conhecidas.

### 🧪 Dados de Teste
- Arquivos `.json` com metadados e estruturas sem rótulos.
- A previsão submetida deve conter as **coordenadas (x, y, z)** para cada nucleotídeo.

---

## 🔍 Metodologia

A solução implementada segue uma **pipeline modular** que pode ser dividida nas seguintes etapas:

### 1. 🧠 Análise de MSA
- A partir do MSA, foram extraídas **estatísticas de coevolução** e padrões de conservação.
- Inferência de **prováveis pares de contato estrutural**, com base em medidas estatísticas (como frequência conjunta e covariância).

### 2. 🧱 Geração de Estrutura 3D
- Utilizando os pares de contato inferidos, uma matriz de distâncias é estimada.
- Técnicas de otimização e métodos geométricos (como MDS – Multidimensional Scaling) são aplicados para estimar as coordenadas 3D dos nucleotídeos.

### 3. 🧪 Avaliação
- As estruturas geradas são comparadas com as reais (no conjunto de validação) utilizando a métrica **TM-score**, que avalia similaridade estrutural.
- Também foi usado o **algoritmo de Kabsch** para alinhar rigidamente estruturas previstas e reais.

### 4. 🧬 Visualização
- As estruturas foram visualizadas com a biblioteca **Py3Dmol**, permitindo inspeção visual dos modelos gerados.
  
![image](https://github.com/user-attachments/assets/426a3699-7c8b-418f-bdf2-b1788e008e51)

---

## 📈 Principais Resultados

- A pipeline foi capaz de capturar corretamente diversos padrões estruturais típicos de RNA (como alças e hélices).
- Obteve-se TM-scores consistentes acima de 0.4 para muitas sequências, o que indica **semelhança estrutural razoável** com as estruturas reais.
- O uso do MSA provou-se crucial para revelar interações estruturais conservadas.

---

## 🧪 Tecnologias Utilizadas

- **Python 3.10+**
- `numpy`, `pandas`, `scikit-learn`
- `matplotlib`, `plotly`, `py3Dmol`
- `Biopython`
- Ferramentas externas: **TM-score**, **US-align**

---

## ▶️ Como Executar

1. Clone este repositório:

```bash
git clone https://github.com/seu-usuario/rna-3d-folding.git
cd rna-3d-folding
