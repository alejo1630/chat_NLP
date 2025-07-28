# 🧠 Chat_NLP: A Personalized WhatsApp Chatbot

## 📌 Description

This project explores the creation of a neural conversational model trained on real WhatsApp chat history. The goal is to build a chatbot that mimics the communication style of the user **Alejandro** generating context-aware responses based on previous messages using a sequence-to-sequence (seq2seq) architecture with LSTM networks.

## 📁 Dataset

> 🔒 **Note:** The WhatsApp chat dataset used in this project contains personal and private information. For privacy and security reasons, the dataset is **not included** in this repository. Only the preprocessing and training code is provided so users can replicate the pipeline with their own data.


The dataset is a WhatsApp chat export in `.txt` format between two users:
- **Linda**
- **Alejandro** (target speaker)

The chat history was parsed and cleaned to extract valid dialogue turns, excluding media messages and deleted content. From 203,094 messages, over 40,000 valid input–response pairs were generated for training the model.

## ✅ What’s Implemented

- 📄 **Chat Parsing:** Regex-based extraction of messages, users, and timestamps.
- 🔁 **Dialogue Turn Construction:** Consecutive messages are grouped to form coherent turns.
- 🔄 **Input–Target Pairing:** Each message by Alejandro is paired with the previous message by Linda.
- 🧠 **Seq2Seq Model:** Encoder–decoder architecture using LSTM layers implemented with TensorFlow/Keras.
- 🧪 **Inference Pipeline:** Real-time decoding loop to generate responses token-by-token.
- 💬 **Interactive Chat Interface:** A console-based chatbot (Alejo_Bot) simulates WhatsApp-style conversation.

## 🛠️ Tools

- Python
- TensorFlow / Keras
- NumPy, Pandas, re
- Google Colab (for training and experimentation)
- WhatsApp exported `.txt` file

> ⚠️ **Note:** Due to GPU memory limitations on Google Colab, the model was trained with:
> - `batch_size = 32`  
> - `embedding_dim = 128`  
> - `lstm_units = 256`  
>
> These values were selected to balance training feasibility with performance.

## 📊 Results

- Model trained for 5 epochs with the limited configuration above.
- Final **validation perplexity**: ~98.76.
- Although accuracy metrics are low (due to the nature of free-form language generation), the model is able to generate plausible, stylistically aligned responses.
- Example:
  ```
  Input: Hola
  Output: cómo vas?
  ```

## 🔮 Future Work

- 🔁 Train for more epochs and fine-tune hyperparameters (e.g., embedding size, LSTM units).
- 📈 Evaluate using BLEU, ROUGE, and human evaluation metrics for dialogue quality.
- 🌍 Expand to multilingual models and multi-speaker chat modeling.
- 📱 Deploy via a frontend interface (e.g., Streamlit, Telegram bot, or WhatsApp bot via Twilio).
- 🤗 Explore transfer learning with pre-trained LLMs (e.g., T5, BART, GPT) for improved generation.

## 🧾 Conclusion

This project demonstrates the feasibility of training a neural chatbot from personal chat history using classical seq2seq architecture. It showcases end-to-end pipeline development — from data wrangling and preprocessing to model training and interactive inference — making it a strong baseline for personalized chatbot applications. While the current implementation is basic, it provides a solid foundation for further experimentation and real-world deployment.
