This project explores fine-tuning large language models for sentiment classification under limited GPU resources. The initial goal was to fine-tune LLaMA 2 (7B Chat) on a Romanized Nepali restaurant review dataset using parameter-efficient fine-tuning techniques such as LoRA and QLoRA.

The dataset used was amirpoudel/nepal-romanized-restaurant-reviews from Hugging Face, which contains Romanized Nepali restaurant reviews labeled with three sentiment classes: positive, neutral, and negative.

Due to the 16GB VRAM limitation of Google Colab GPUs, full fine-tuning of LLaMA 2 was not feasible. Even with LoRA and QLoRA, the LLaMA-2-7B-Chat model consistently ran into out-of-memory (OOM) issues on both the free and Pro versions of Google Colab. This led to further research into smaller, more resource-efficient models suitable for sequence classification tasks.

As a result, the project pivoted to distilbert-base-uncased, a lightweight, distilled version of BERT optimized for sentence-level tasks such as sentiment analysis. DistilBERT significantly reduced memory requirements while maintaining strong performance, making it well-suited for fine-tuning on the available hardware.

The final implementation successfully fine-tunes DistilBERT for sentiment classification of Romanized Nepali text, demonstrating an effective trade-off between model size, performance, and hardware constraints.

Key Highlights

Explored LoRA and QLoRA for efficient fine-tuning of large language models

Identified practical GPU memory limitations when working with 7B parameter models

Selected DistilBERT as a resource-efficient alternative for sentiment classification

Fine-tuned on a Romanized Nepali sentiment dataset

Demonstrates real-world decision-making in model selection under hardware constraints
