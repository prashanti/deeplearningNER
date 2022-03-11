## Model Training

`Bi-GRU.ipynb` provides the option to run different model architecture by changing the CONFIG parameters inside the notebook.

+ Our Bi-GRU architecture utilizes one of the following three embeddings:
  1. CRAFT
    - This is our supervised embedding whose weights (or embedding values) are learnt during the model training on our inputs.
    - CRAFT has 100 dimensional output representation.
  2. GLOVE
    - This is a 300 dimensional vector representations for words obtained from training on cased common crawled corpus with 840B tokens and 2.2M vocabulary.
  3. ELMO
    - This is a 1024 dimensional vector representations for words obtained from training on 1B Word Benchmark, which consists of approximately 800M tokens of news crawl data.

+ Change `EMBEDDING` to one of `CRAFT`, `GLOVE` or `ELMO`.
+ If you train the model with different configurations but same embedding, change the `EXPERIMENT_NO` accordingly. This variable is later used to store trained model along with prediction results and evaluation reports.
+ If your kernel dies due to memory issues, increase the `OUTPUT_PARTS` in `CONFIG` variable to a higher value. `OUTPUT_PARTS` splits the test data into different parts and prediction are made on these smaller parts. The predicted array are saved as *.npy files in parts. Each part is processed for evaluation and merged together to calculate the evaluation metrics.
+ `CONFIG.INPUT_LAYERS` represents the different input pipelines for the model. Set layer value to `FALSE` to remove the input sequence from the pipelines or `TRUE` to add the input sequence to the pipelines.
+ `Evaluate model performance` cell block saves model predictions and reports in model.name directory inside `/data/model_output`. The directory includes prediction_{part}.npy, model.png, classification report and report summary.
