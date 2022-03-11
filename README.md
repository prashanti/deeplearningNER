## NEural Models for Ontological annotation (NEMO)


In order to replicate or re-run the experiments as described in [this](https://https://github.com/prashanti/deeplearningNER) paper, clone this repository.

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
