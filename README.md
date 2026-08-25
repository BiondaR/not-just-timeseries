<div align="center">

# not-just-timeseries

**A multimodal hub tailored for time series and compatible with diverse multimedia**

A collection of small, focused Python packages for time series feature extraction, distance/similarity computation, and unsupervised ranking/re-ranking.

</div>

---

## ✨ Before anything else

Most of these methods were written and tested with time series in mind, but the underlying math (distances, ranking, re-ranking) rarely cares what kind of data it's looking at. A lot of what's here works just as well on images, text embeddings, or any other vector-representable data. Don't let the name fool you.

Each package is kept in its own repository and its own Python environment on purpose. Dependencies like `sktime`, `aeon`, and `tslearn` don't always play well together, so isolation beats one giant fragile package.

---

## ✨ Repositories

### Distance & Ranking

| Repo | Description | Python | Link |
|---|---|:---:|:---:|
| **tsdist** | Distance & similarity metrics for vectors, time series, and ranked lists (Euclidean, DTW, RBO, Kendall...), plus an ANN search engine wrapping FAISS/HNSWLib/Annoy/BallTree | 3.10+ | [🔗 repo](https://github.com/BiondaR/tsdist) |
| **scikit-pyudlf** | sklearn-style fork of pyUDLF (Unsupervised Distance Learning Framework) — re-ranking methods like LHRR, RDPAC, RFE via a `fit`/`transform` interface, with source-build support | 3.10+ | [🔗 repo](https://github.com/BiondaR/scikit-pyudlf) |

### Feature Extraction

| Repo | Description | Python | Link |
|---|---|:---:|:---:|
| **ts-text-features** | Converts numeric time series into textual representations (SAX, SFA, ABBA, natural-language templates) and extracts numeric features from that text: BoW (word/char n-grams), TF-IDF, BERT, Word2Vec, BOSS, WEASEL | 3.9+ | [🔗 repo](https://github.com/BiondaR/ts-text-features) |
| _coming more soon_ | | | |

---

## ✨ Choosing a package

```
Need distances/similarity between series or ranked lists?     → tsdist
Need to re-rank / refine distances unsupervised?              → scikit-pyudlf
Need to extract features from raw time series?                → ts-*-features (soon)
```

---

## ✨ Design principles

- **One package, one job.** Each repo does a single thing well instead of one monolith trying to satisfy every dependency at once.
- **Consistent API.** Where it makes sense, packages follow an sklearn-style `fit` / `transform` / `fit_transform` interface, so they compose naturally in pipelines.
- **Isolated environments.** Conflicting dependencies (`sktime`, `aeon`, `tslearn`, etc.) are the reason these live in separate repos rather than separate modules of one package.
- **Data-agnostic where possible.** Time series first, but built to admit other data types when possible.

---

## ✨ Author

**Bionda Rozin**

PhD Student in Computer Science, DEMAC/UNESP

`bionda.rozin@unesp.br`

---

## ✨ License

Each repository carries its own license. Check the individual repo before using it.
