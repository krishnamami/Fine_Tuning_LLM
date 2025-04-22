
  # Fine-Tuning Large Language Models (LLMs) with QLoRA on SageMaker

# Project Overview
This project demonstrates **fine-tuning Large Language Models (LLMs)** using QLoRA (Quantized Low-Rank Adaptation) . It is optimized for enterprise-scale scenarios with limited compute, leveraging 4-bit quantization and adapter-based training.

#Business Context
As businesses look to integrate Generative AI into workflows, efficient fine-tuning of open-source foundation models becomes critical. This project was part of nitiative to evaluate scalable and cost-effective fine-tuning approaches for **custom in-domain LLMs**.

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

  A task-specific dataset[gretelai/synthetic_text_to_sql](https://huggingface.co/datasets/gretelai/synthetic_text_to_sql) from Hugging Face is curated and preprocessed to 
  enable effective supervised fine-tuning of the LLM.

* Foundational Model:

   A pre-trained foundation model [gemma-2b-it](https://huggingface.co/google/gemma-2b-it) is selected from the Hugging Face model hub to serve as the starting point for 
 fine- tuning.

* Fine-Tuning with Hugging Face Libraries:
   * Quantization: Applied to reduce the memory footprint.
   * QLoRA (Quantized Low-Rank Adaptation): Used to enable memory-efficient supervised fine-tuning by injecting trainable LoRA weights into the base model.
* Model Evaluation :

   The fine-tuned model's outputs are evaluated to assess its performance on the target tasks. This involves both quantitative metrics and qualitative analysis to ensure 
   alignment with project goals.

Project Structure:
Fine_Tuning_LLM/


├── qlora.py                 # Main training script (QLoRA + PEFT)

├── requirements_local.txt   # SageMaker packages

├── requirements.txt         # Required packages for local or SageMaker execution

├── gemma.ipynb              # Script to train and evaluate the model


└── README.md                # Project documentation

* References:

PEFT (Parameter Efficient Fine Tuning)

## Related Projects

[Distributed ML SageMaker Pipeline](https://github.com/krishnamami/Distributed_ML_Sagemaker_Pipelines)

Krishna Goud
Head of Data Engineering & MLOps | Rocket LA [LinkedIn](https://www.linkedin.com/in/krishnagoud)

Delivering $4B+ business impact through real-time AI pipelines and scalable GenAI foundations


