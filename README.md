# Persian Poetry Generation with GPT-2

Fine-tune [`HooshvareLab/gpt2-fa`](https://huggingface.co/HooshvareLab/gpt2-fa) to generate Persian poetry conditioned on a poet name.

## Notebook

Open `persian-poetry-gpt2-finetuning.ipynb` in Google Colab or Jupyter. The notebook includes saved cell outputs from the completed run so readers can inspect the training metrics, plots, and generated examples without rerunning every cell.

## Resource-aware training settings

The example uses a maximum sequence length of 256 tokens and caps training at 2,500 optimizer steps to fit limited GPU memory and runtime (for example, a Tesla T4 in a free Colab session). If you have more compute resources, you can experiment with `MAX_LENGTH = 512`, more epochs, and a larger `MAX_STEPS`; set `MAX_STEPS = -1` to disable the positive step cap and train for the configured number of epochs. Longer sequences and more training increase memory use and runtime and do not guarantee better results. Evaluate validation loss and inspect generated poetry.

## Dataset

The notebook uses the public [Chronological Persian Poetry Dataset](https://github.com/aghasemi/ChronologicalPersianPoetryDataset). It downloads the dataset when it is not available locally.

## Run

1. Open the notebook in Google Colab or a Jupyter environment.
2. Use a Python environment with the packages listed in `requirements.txt`.
3. Run cells in order. A CUDA GPU is recommended.
4. The trained model is saved under `artifacts/persian-poetry-gpt2` by default. Model weights and checkpoints are not included in this repository because they can be large.

## Notes

- Saved notebook outputs are included for demonstration; rerun the notebook to reproduce results in your environment.
- Output metrics and generation quality depend on dataset version, random seed, software versions, and hardware.
- Generated poetry may contain repetition, errors, or text resembling the training corpus.
