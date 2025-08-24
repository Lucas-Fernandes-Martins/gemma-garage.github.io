---
layout: splash
title: "💎 Gemma Garage"
subtitle: "Democratizing LLM Fine-tuning"
header:
  overlay_color: "#5e616c"
  overlay_image: https://gist.github.com/user-attachments/assets/5a2f4068-05dc-4b47-897c-b25c966bd266
  overlay_filter: 0.5
  actions:
    - label: "🚀 Try Gemma Garage"
      url: "https://gemma-garage.web.app"
      class: "btn btn--primary btn--large"
    - label: "📖 View on GitHub"
      url: "https://github.com/Gemma-Garage"
      class: "btn btn--inverse btn--large"
excerpt: "Google Summer of Code 2025 @ Google DeepMind<br>Fullstack platform for democratizing LLM fine-tuning with Gemma models"
intro: 
  - excerpt: 'Gemma Garage is a comprehensive platform that allows you to create augmented datasets from structured or unstructured data, fine-tune Gemma models, and deploy them seamlessly. Built on Google Cloud infrastructure with open-source foundations.'
feature_row:
  - image_path: https://via.placeholder.com/300x200/FF6B6B/FFFFFF?text=Data+Processing
    alt: "Data Processing"
    title: "🔄 Smart Data Processing"
    excerpt: "Extract and augment data from PDFs, DOCs, JSONs, and more using Meta's synthetic-data-kit and Gemini 2.5 Flash."
    url: "/architecture/"
    btn_label: "Learn More"
    btn_class: "btn--primary"
  - image_path: https://via.placeholder.com/300x200/4ECDC4/FFFFFF?text=Fine-tuning
    alt: "Fine-tuning"
    title: "⚡ Efficient Fine-tuning"
    excerpt: "Leverage Unsloth AI for fast, memory-efficient fine-tuning of Gemma models with real-time progress tracking."
    url: "/architecture/"
    btn_label: "Learn More"
    btn_class: "btn--primary"
  - image_path: https://via.placeholder.com/300x200/45B7D1/FFFFFF?text=Deployment
    alt: "Deployment"
    title: "🚀 Seamless Deployment"
    excerpt: "Push your fine-tuned models to Hugging Face Hub or test them directly with our built-in inference engine."
    url: "/architecture/"
    btn_label: "Learn More"
    btn_class: "btn--primary"
feature_row2:
  - image_path: https://via.placeholder.com/400x300/96CEB4/FFFFFF?text=Research
    alt: "Research"
    title: "🧠 Cutting-edge Research"
    excerpt: 'Our research phase explored **Reinforcement Learning** and **Prompt Optimization** techniques, achieving remarkable results: improving Gemma 3 1B from **<3% to >50% accuracy** on GSM8K math problems using Group Relative Policy Optimization (GRPO).'
    url: "/research/"
    btn_label: "Read Research"
    btn_class: "btn--primary"
feature_row3:
  - image_path: https://via.placeholder.com/400x300/FFEAA7/333333?text=Open+Source
    alt: "Open Source"
    title: "🤝 Open Source Contributions"
    excerpt: 'Beyond Gemma Garage, we actively contribute to the open-source community. Check out our contributions to Meta\'s **synthetic-data-kit** and other projects that benefit the entire ML community.'
    url: "/open-source/"
    btn_label: "View Contributions"
    btn_class: "btn--primary"
---

{% include feature_row id="intro" type="center" %}

## 🎯 What Makes Gemma Garage Special?

Gemma Garage bridges the gap between complex LLM fine-tuning and accessibility. Whether you're a researcher, developer, or enthusiast, our platform provides:

- **No-code data processing** from various file formats
- **Automated dataset augmentation** using state-of-the-art LLMs
- **Optimized fine-tuning** with memory-efficient techniques
- **Real-time monitoring** of training progress
- **Seamless model deployment** to Hugging Face Hub

{% include feature_row %}

## 🎥 See It in Action

{% include video id="1AZTpRR9KGo" provider="youtube" %}

{% include feature_row id="feature_row2" type="left" %}

{% include feature_row id="feature_row3" type="right" %}

## 🏗️ Built With Modern Tech Stack

- **Frontend**: React + Firebase (Authentication & Database)
- **Backend**: FastAPI deployed on Google Cloud Run
- **Processing**: Meta's synthetic-data-kit + Gemini 2.5 Flash
- **Training**: Unsloth AI for efficient Gemma fine-tuning
- **Infrastructure**: Google Cloud Platform
- **Integration**: Hugging Face Hub for model sharing

## 📊 Proven Results

Our research demonstrates the effectiveness of modern fine-tuning techniques:

- **50x improvement** in math reasoning accuracy (3% → 50%+)
- **Efficient training** on consumer hardware
- **Format consistency** improvement through RL
- **Domain-specific optimization** for mathematical reasoning

---

*This project is part of **Google Summer of Code 2025** in collaboration with **Google DeepMind**. Learn more about our journey through our [blog posts](https://medium.com/@lucasfmartins) and explore the complete [codebase](https://github.com/Gemma-Garage).*
title: "💎 Gemma Garage"
subtitle: "Google Summer of Code (GSoC) 2025 @ Google DeepMind"
author_profile: true
---

# 🚀 What's Gemma Garage?

[Gemma Garage](https://gemma-garage.web.app/home) is a **fullstack development + research project** started in **Google Summer of Code 2025**, in collaboration with **Google DeepMind**.  

Its mission is to **democratize LLM fine-tuning** using Google’s [Gemma models](https://deepmind.google/models/gemma/).  
It runs on **Google Cloud Run + Firebase**, and builds upon open-source libraries like [Unsloth](https://github.com/unslothai/unsloth) and [Meta’s synthetic-data-kit](https://github.com/meta-llama/synthetic-data-kit/issues).

👉 Try it here: [gemma-garage.web.app](https://gemma-garage.web.app)  
👉 Codebase: [github.com/Gemma-Garage](https://github.com/Gemma-Garage)

[![Gemma Garage Demo](https://img.youtube.com/vi/1AZTpRR9KGo/0.jpg)](https://www.youtube.com/watch?v=1AZTpRR9KGo)
