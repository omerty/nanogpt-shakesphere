# NanoGPT Shakespeare

This project demonstrates a minimal implementation of GPT-like models to generate text based on Shakespeare's works. It includes two implementations: 

1. **Bigram Language Model:** A simpler model with direct token embeddings.
2. **GPT Language Model:** A transformer-based implementation with multi-head self-attention.

## Features

- **Bigram Model:** Direct token-to-token prediction.
- **GPT Model:** Transformer with positional embeddings, self-attention, and feed-forward layers.
- Customizable hyperparameters for training and evaluation.
- Generates text based on training data.

## Setup

1. Clone the repository:
    ```bash
    git clone https://github.com/omerty/nanogpt-shakespeare.git
    cd nanogpt-shakespeare
    ```

2. Install the required dependencies:
    ```bash
    pip install torch
    ```

3. Download the dataset:
    ```bash
    wget https://raw.githubusercontent.com/karpathy/char-rnn/master/data/tinyshakespeare/input.txt
    ```

4. Place the `input.txt` file in the same directory as the script.

## Usage

### Bigram Language Model

1. Run the Bigram Language Model:
    ```bash
    python bigram.py
    ```

2. Adjust hyperparameters in the `bigram.py` file for custom configurations.

### GPT Language Model

1. Run the GPT Language Model:
    ```bash
    python gpt.py
    ```

2. Adjust hyperparameters in the `gpt.py` file for custom configurations.

## File Structure

- `bigram.py`: Contains the Bigram Language Model implementation.
- `gpt.py`: Contains the GPT-like Transformer implementation.
- `input.txt`: Dataset (Shakespeare's text).

## Hyperparameters

Modify the following hyperparameters in the scripts for customization:

- `batch_size`: Number of sequences processed in parallel.
- `block_size`: Maximum context length for predictions.
- `learning_rate`: Learning rate for the optimizer.
- `max_iters`: Total training iterations.
- `n_embd`: Embedding dimension (GPT model only).
- `n_head`: Number of attention heads (GPT model only).
- `n_layer`: Number of transformer blocks (GPT model only).

## Model Details

### Bigram Model

- A simple embedding-based model.
- Directly maps token embeddings to the next token.

### GPT Model

- Transformer architecture.
- Includes multi-head self-attention and feed-forward layers.
- Positional embeddings to handle token positions.

## Text Generation

Both models support generating text:

1. Modify the `max_new_tokens` variable to control the length of generated text.
2. Use `decode()` to convert the generated token indices into readable text.

## Examples

- **Bigram Model**:
    ```python
    context = torch.zeros((1, 1), dtype=torch.long, device=device)
    print(decode(m.generate(context, max_new_tokens=500)[0].tolist()))
    ```

- **GPT Model**:
    ```python
    context = torch.zeros((1, 1), dtype=torch.long, device=device)
    print(decode(m.generate(context, max_new_tokens=500)[0].tolist()))
    ```
