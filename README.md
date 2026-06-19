# Multilingual Health QA System

## Project Overview
This project develops a sequence-to-sequence Transformer model (T5) designed to provide accurate, structured medical responses for multilingual healthcare queries. The model was optimized specifically for clinical diagnostic accuracy through a two-phase training lifecycle.

## Training Methodology
The training was conducted in two distinct phases to balance linguistic generalization with clinical precision:

* **Phase 1: Broad Domain Adaptation**
    Focus on multilingual linguistic grounding (Akan, Amharic, Luganda). We utilized a multi-checkpoint `active_run` strategy to ensure stable convergence across the broad dataset.
* **Phase 2: Targeted Clinical Fine-Tuning**
    Specialized adaptation to the MSRH (Medical System Response Hierarchy). We manually refined the model weights to ensure outputs meet strict diagnostic formatting requirements.

## Technical Specifications
- **Architecture:** `T5ForConditionalGeneration`
- **Model Parameters:** `d_model: 512`, `num_heads: 8`
- **Vocabulary:** 32,128 tokens
- **Infrastructure:** Fine-tuned on Google Colab with integrated tracking of training lifecycle metrics via `trainer_state.json`.

## Results
The model demonstrates consistent loss reduction and successful adaptation to medical terminology.

![Training Loss Curve](assets/loss_curve.png)

## Reproducibility
The project is fully reproducible via the provided Google Colab notebook. 
[Click here to run the notebook on Colab](INSERT_YOUR_COLAB_LINK_HERE)

## Ethical Considerations
This model is designed to assist in healthcare settings. We recognize the risks of misinformation in medical AI and prioritize accuracy, linguistic inclusivity, and bias mitigation for the local populations in the Kampala-Entebbe corridor.
