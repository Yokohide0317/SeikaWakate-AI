# SeikaWakate-AI
2024年九州支部主催、「話題のAIツールで生化学を遊び倒せ！」用のリポジトリ


# ダウンロードデータ

## 1. bulk RNA-Seq

| File | Description |
|:---:|:---:|
| [bulkRNASeq_TPM-prep-HT.csv](https://github.com/Yokohide0317/SeikaWakate-AI/blob/main/data/bulkRNASeq_TPM-prep-HT.csv) | HT-29(ヒト大腸がん細胞株)遺伝子発現解析 |

- GSE: ブドウ種子エキス
- OPC: オリゴメリック・プロアントシアニジン

### 手順（例）
| No. | 手順 | キーワード |
| :---: | --- | --- |
| 1 | データの読み込み | `pandas` |
| 2 | グループ列の追加 |  |
| 3 | `TGFB3`を棒グラフに | `matplotlib`, `seaborn` |
| 4 | 3をカスタマイズ |  |

<details>
<summary>Cite</summary>
Ravindranathan P, Pasham D, Balaji U, Cardenas J, Gu J, Toden S, Goel A. Mechanistic insights into anticancer properties of oligomeric proanthocyanidins from grape seeds in colorectal cancer. Carcinogenesis. 2018 May 28;39(6):767-777. doi: 10.1093/carcin/bgy034. PMID: 29684110; PMCID: PMC5972632.
</details>

---

## 2. Microbiome

| File | Description |
|:---:|:---:|
| [microbiome_level5_counts.csv](https://github.com/Yokohide0317/SeikaWakate-AI/blob/main/data/microbiome_level5_counts.csv) | 膵臓がん患者の腸内細菌叢データ |

- PDAC: 膵管腺癌(Pancreatic Ductal Adenocarcinoma)
- CTRL: コントロール

### 手順（例）

| No. | 手順 | キーワード |
| :---: | --- | --- |
| 1 | データの読み込み | `pandas` |
| 2 | サンプルごとに百分率化 | 合計値を`100`に揃える |
| 3 | グループ列の追加 |  |
| 4 | `d__Bacteria;p__Firmicutes_D;c__Bacilli;o__Lactobacillales;f__Lactobacillaceae`<br>を箱ひげ図に | `matplotlib`, `seaborn` |
| 5 | 積み上げ棒グラフで、サンプルごとの組成を可視化 |  |

<details>
<summary>Cite</summary>
Nagata N, Nishijima S, Kojima Y, Hisada Y, Imbe K, Miyoshi-Akiyama T, Suda W, Kimura M, Aoki R, Sekine K, Ohsugi M, Miki K, Osawa T, Ueki K, Oka S, Mizokami M, Kartal E, Schmidt TSB, Molina-Montes E, Estudillo L, Malats N, Trebicka J, Kersting S, Langheinrich M, Bork P, Uemura N, Itoi T, Kawai T. Metagenomic Identification of Microbial Signatures Predicting Pancreatic Cancer From a Multinational Study. Gastroenterology. 2022 Jul;163(1):222-238. doi: 10.1053/j.gastro.2022.03.054. Epub 2022 Apr 8. PMID: 35398347.
</details>

---

## 3. single cell RNA-Seq
| File | Description |
|:---:|:---:|
| [scRNASeq_counts_pbmc_preped.csv](https://github.com/Yokohide0317/SeikaWakate-AI/blob/main/data/scRNASeq_counts_pbmc_preped.csv) | 末梢血のシングルセルごとのカウントデータ |
| [scRNASeq_counts_pbmc_preped.csv](https://github.com/Yokohide0317/SeikaWakate-AI/blob/main/data/scRNASeq_cluster_pbmc_preped.csv) | `scRNASeq_counts_pbmc_preped.csv`の細胞種アノテーション |

### 手順（例）

| No. | 手順 | キーワード |
| :---: | --- | --- |
| 1 | データの読み込みx2 | `pandas` |
| 2 | Cellごとに発現量を全マッピング数で補正 | CPM補正(10の6乗) |
| 3 | `log1p`で対数変換 | `numpy` |
| 4 | UMAPで次元削除 & 細胞種データと結合 | `umap` |
| 5 | UMAP結果を散布図で可視化 | `matplotlib`, `seaborn` |
| 6 | t-SNEで次元削除 & 細胞種データと結合 | `sklearn` |
| 7 | t-SNE結果を散布図で可視化 | `matplotlib`, `seaborn` |
| 8 | 細胞種ごとに`IL7R`の発現量を`violinplot`で可視化 | `seaborn` |


<details>
<summary>Cite</summary>
- Satija, R., Farrell, J., Gennert, D. et al. Spatial reconstruction of single-cell gene expression data. Nat Biotechnol 33, 495–502 (2015). https://doi.org/10.1038/nbt.3192

- [Preprocessing and clustering 3k PBMCs](https://scanpy-tutorials.readthedocs.io/en/latest/pbmc3k.html)
</details>


