## NEural Models for Ontological annotation (NEMO)

Annotating scientific literature with ontology concepts is a critical task in biology and several other domains for knowledge discovery. Ontology based annotations can power large-scale comparative analyses in a wide range of applications ranging from evolutionary phenotypes to rare human diseases to the study of protein functions. Computational methods that can tag scientific text with ontology terms have included lexical/syntactic methods, traditional machine learning, and most recently, deep learning.

Here, we present state of the art **deep learning architectures based on Gated Recurrent Units (GRU)** for annotating text with ontology concepts. We use the Colorado Richly Annotated Full Text Corpus (CRAFT) as a gold standard for training and testing. We explore a number of additional information sources including NCBI's BioThesauraus and Unified Medical Language System (UMLS) to augment information from CRAFT for increasing prediction accuracy. **Our best model results in a 0.84 F1 and semantic similarity**.

#### Deep Learning Architecture
[This](./data/model_output/architecture.svg) figure represents our deep learning architecture based on Bidirectional GRU (Bi-GRU) which consists of three major components: 1. Input pipelines 2. Embeddings/Latent Representations and 3. Sequence Modeler.


In order to replicate or re-run the experiments as described in [this](https://www.github.com/prashanti/deeplearningNER) paper, clone this repository.

#### To perform model training with available train and test dataset

1. Install the required python packages by running the command:

  ```
  pip install -r requirements.txt
  ```
2. To train the model with GloVe embeddings, you need to download the embeddings before passing the weights to the model. We used Glove 300 dimensional embeddings trained on 840B tokens from cased Common Crawl.
  + Run `glove_txt_to_bin.ipynb` notebook from `/src/preprocessing` directory.
  + To train with a different glove embedding, replace `FILENAME` variable with one of the filenames from [huggingface](https://huggingface.co/stanfordnlp/glove/tree/main). For example, change `FILENAME` to `glove.42B.300d.zip`.
3. Run `Bi-GRU.ipynb` from `/src/model_training` directory.

**Note:** These experiments are carried out on single **Tesla V100-SXM2-16GB** GPU and **8 core** CPU with **51.01 GB RAM**.

### Support or Contact

Email: &emsp;p_devkota@uncg.edu
&emsp;&emsp;&emsp;&emsp;sdmohant@uncg.edu
&emsp;&emsp;&emsp;&emsp;p_manda@uncg.edu
