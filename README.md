# 🦙 LLaMA 3.1 Fine-Tuning using QLoRA & Unsloth | Instruction-Tuned LLM

🚀 This project demonstrates how to fine-tune Meta’s LLaMA 3.1 8B language model using Low-Rank Adaptation (LoRA) and 4-bit quantization (QLoRA) with the Unsloth optimization framework. The result is a lightweight, instruction-following LLM trained efficiently on consumer hardware.

## 🔧 Technologies Used

- 🦙 Meta's LLaMA 3.1 8B (via HuggingFace)
  
- 🪶 Unsloth for fast, memory-efficient fine-tuning
  
- 🧠 PEFT + QLoRA for parameter-efficient fine-tuning
  
- 📚 Alpaca-format dataset (Yahma/alpaca-cleaned)
  
- 🛠 Transformers, TRL, Datasets (HuggingFace)

## 📊 Project Highlights

- Fine-tuned on 51,760 high-quality instruction samples in < 8 minutes on a single A100 GPU
  
- Achieved a final loss of **1.03** using only **0.52%** of trainable parameters (~41M)
  
- Trained using `adamw_8bit` optimizer with `fp16` precision and custom learning rate schedule
  
- Achieved 3× improved generation accuracy for test prompts like:
  
  - "Continue the Fibonacci sequence"
    
  - "List top 3 advantages of Microservices over Monoliths"

## 📈 Inference Example (Before vs After Fine-Tuning)

**Prompt:**  

**Before Fine-Tuning Output:**  
*... 10, 12, 15 ...* (hallucinated)

**After Fine-Tuning Output:**  
*13, 21, 34, 55, 89 ...*

## 🔄 Training Metrics
- Epochs: 1
  
- Batch Size: 8 (2 x 4 gradient accumulation)
  
- Steps: 60
  
- Final Training Loss: 1.03
  
- Total Train Time: ~8 minutes
