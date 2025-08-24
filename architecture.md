---
layout: single
title: "⚙️ Architecture"
permalink: /architecture/
---

<img src="https://gist.github.com/user-attachments/assets/5a2f4068-05dc-4b47-897c-b25c966bd266" alt="architecture" />

### Modules
- **Frontend** → React + Firebase
- **Backend** → FastAPI + Cloud Run
- **Data Augmentation** → [synthetic-data-kit](https://github.com/meta-llama/synthetic-data-kit) + Gemini 2.5 Flash
- **Fine-tuning** → [Unsloth AI](https://github.com/unslothai/unsloth/blob/main/unsloth/trainer.py)
- **Inference** → Compare base vs fine-tuned models
- **Hugging Face Integration** → OAuth + Hub upload
