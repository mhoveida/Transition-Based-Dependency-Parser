## Transition-Based Dependency Parser

This project is a way to teach a computer how to understand the "skeleton" of a sentence. Instead of just reading words, the model figures out which words depend on each other-like how an adjective describes a noun or a verb shows what a subject is doing.

### What does it do?

* **The "Shift-Reduce" Strategy**: The parser moves through a sentence using a **stack** (to hold words it's currently thinking about) and a **buffer** (words it hasn't looked at yet).
* **Three Main Moves**:
* **Shift**: Moves a word from the buffer onto the stack.
* **Left-Arc**: Creates a link where the current word points to a previous word.
* **Right-Arc**: Creates a link where a previous word points to the current one.


* **Neural Network "Brain"**: I built a neural network in **PyTorch** that looks at the top 3 words on the stack and the first 3 in the buffer to "guess" which of these moves is the best one to make next.

### How to run it

1. **Build the Dictionary**: Run `get_vocab.py` so the model learns all the unique words and POS (Part of Speech) tags in your data.
2. **Extract Features**: Run `extract_training_data.py` to turn regular sentences into a format (NumPy arrays) the computer can actually learn from.
3. **Train the Model**: Run `train_model.py` to let the model practice and save its progress into a file called `model.pt`.
4. **Test It Out**: Run `evaluate.py` to see how accurate the model is by comparing its guesses to the correct answers.

### Requirements

* **Python 3**
* **PyTorch** (to build and run the neural network)
* **NumPy** (to handle the data matrices)
