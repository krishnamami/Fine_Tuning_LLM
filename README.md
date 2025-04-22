# Fine_Tuning_LLM

# Project Overview
This project focuses on fine-tuning a foundational large language model (LLM) using efficient and scalable methods. 

## Popular Fine-Tuning Techniques
To adapt large language models (LLMs) for specific downstream tasks efficiently, two widely adopted parameter-efficient fine-tuning techniques are used:
  * Prompt Tuning:

     * Instead of updating model weights, prompt tuning appends trainable tokens (prompt tuning parameters) to the input.

     * The underlying model remains unchanged (i.e., its weights are frozen), and only these additional prompt tokens are optimized during training.
     * Disadvatnges: As we optimze small token of input tokens this may not be ideal for complex tasks

* LORA(Low Rank Adoption):

  * LoRA injects small trainable weight matrices into the frozen pre-trained model layers.
  * During fine-tuning, only these LoRA weights are updated while the original model parameters remain unchanged.
 
    ![image](https://github.com/user-attachments/assets/e54c6c49-dd09-423d-a02e-3b9d0fd02f22)
    
# Project Flow:

* Task:

  A task-specific dataset[gretelai/synthetic_text_to_sql](https://huggingface.co/datasets/gretelai/synthetic_text_to_sql) from Higging Face is curated and preprocessed to enable effective supervised fine-tuning of the LLM.

* Foundational Model:

A pre-trained foundation model [gemma-2b-it](https://huggingface.co/google/gemma-2b-it) is selected from the Hugging Face model hub to serve as the starting point for fine-tuning.

* Fine-Tuning with Hugging Face Libraries:
   * Quantization: Applied to reduce the memory footprint.
   * QLoRA (Quantized Low-Rank Adaptation): Used to enable memory-efficient supervised fine-tuning by injecting trainable LoRA weights into the base model.
* Model Evaluation :

The fine-tuned model's outputs are evaluated to assess its performance on the target tasks. This involves both quantitative metrics and qualitative analysis to ensure alignment with project goals.
