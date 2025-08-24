# 💎 Gemma Garage - Google Summer of Code (GSoC) 2025 @ Google DeepMind


## What's Gemma Garage?

[Gemma Garage](https://gemma-garage.web.app/home) is a fullstack development and research project started in summer 2025 as part of Google Summer of Code in affilitation with Google DeepMind. Its main goal is to **democratize LLM fine-tuning** leveraging Google's [Gemma](https://deepmind.google/models/gemma/) family 
open-weights models. It is deployed through Google Cloud Run and Firebase, and builts on top of Open Source libraries such as [Unsloth](https://github.com/unslothai/unsloth)
and Meta's [synthetic-data-kit](https://github.com/meta-llama/synthetic-data-kit/issues).

Gemma Garage allows you to create augmented datasets from structured or unstructured data, from JSON to PDF's, augment them into a reasonable sized dataset, and then fine-tune on one of Gemma's models. Finally, you can push your model to your personal hub in Hugging Face, or test inference against the base model directly on the website. 

You can try it out here: https://gemma-garage.web.app

The codebase can be found [here](https://github.com/Gemma-Garage).

You can check out a demo below:

[![Gemma Garage Demo](https://img.youtube.com/vi/1AZTpRR9KGo/0.jpg)](https://www.youtube.com/watch?v=1AZTpRR9KGo)

## The Project

The project had two main stages: the first one was dedicated to coming up with the Gemma Garage platform, adding features such as authentication, Hugging Face integration, data augmentation, etc. The second one was more research oriented, and was mostly spent exploring Reinforcement Learning and Prompt Optmization techniques to boost Gemma's performance on math benchmarks, such as GSM8K and AIME.


## Architecture

<img width="3046" height="1650" alt="image" src="https://gist.github.com/user-attachments/assets/5a2f4068-05dc-4b47-897c-b25c966bd266" />

Gemma Garage's architecture is divided between 5 independent modules:

- Frontend ([gemma-garage-frontend](https://github.com/Gemma-Garage/gemma-garage-frontend)): built with React and deployec through Firebase, it provides the user interface. In order to simplify data storage and authentitication, Firebase Auth abd DB are used to provide email authentication and basic user information storage. While one might argue that a dedicated Database Management System (e.g. Postgres) should have been employed, Firebase's backend as a service options are enough for Gemam Garage's needs as of now. However, As the project scales, using a dedicated Postgres instance will certainly justify the costs.

- Backend ([gemma-garage-backend](https://github.com/Gemma-Garage/gemma-garage-backend)): FastAPI backend, responsible for orchestrating the different services. It is deployed through Cloud Run.

- Data Augmentation ([gemma-garage-augmentation](https://github.com/Gemma-Garage/gemma-garage-augmentation)): built on top of Meta's Open Source [synthetic-data-kit](https://github.com/meta-llama/synthetic-data-kit). It allows to extract data from unstructured or structured files (e.g. PDF, txt, PPT, DOCX, JSON, etc) and augment it using an LLM (gemini-2.5-flash is used). Behind the scenes, the extracted data is divided into chunks, and the LLM produces question and answers (QA) pairs for each chunk, thus generating a structured synthetic dataset which can be used for supervisec fine-tuning.

- Fine-tuning ([gemma-garage-finetuning](https://github.com/Gemma-Garage/gemma-garage-finetuning)): Uses [Unsloth AI](https://github.com/unslothai/unsloth/blob/main/unsloth/trainer.py) Gemma models to speed up training and save VRAM.  At each step of the process, logs are saved to GCP, which are retrived by the frontend. Therefore, the user is constantly notified of progress in the training job, from instantiation to each new loss update.

- Inference ([gemma-garage-inference](https://github.com/Gemma-Garage/gemma-garage-inference)): Simple inference engine so the user can test the fine-tuned model. Completions by the base model are equally displayed in the frontend, so the user can judge how different the fine-tuned model is from the original.

Hugging Face integration: OAuth is leveraged to allow users to connect their accounts to Hugging Face, and thus, push their models to HF hub as soon as training finishes. Alternatively, they can download the adapters files directly in the browser, which can be later merged to the base model.

## Open Source Contributions

In parallel to developping Gemma Garage, I took a deep interest in Meta's Open Source [synthetic-data-kit](https://github.com/meta-llama/synthetic-data-kit). Thus, I commited some time to implemented a new chunking system for summarizing documents, as well as fix bugs reported by users. The PR's merged so far are shown below:

https://github.com/meta-llama/synthetic-data-kit/pull/59

https://github.com/meta-llama/synthetic-data-kit/pull/62

## Research

Once the main features of Gemma Garage were implemented, I turned my attention into researching different fine-tuning and prompt optmization techniques to boost Gemma models performance on math questions. 

Initially, I applied Group Relative Policy Optimization (GRPO) to fine-tune Gemma 3 1B Instruct on the [GSM8K](https://huggingface.co/datasets/openai/gsm8k) dataset, using Gemini 2.5 Flash as judge model and providing only a simple custom rubric. With this setup, I obtained meaningful performance gains, taking the model from below 3% accuracy to over 50%.

The experiment shows that Reinforcement Learning is a viable and effective way to enhance reasoning skills in small language models. GRPO, in particular, proved to be a good fit for LLM-as-Judge setups: since rewards are standardized within groups, fluctuations in the value model’s scoring had little negative effect, as long as the relative ordering of responses was consistent.

Another interesting outcome was the improvement in formatting. While the base model struggled to follow the expected solution format, the fine-tuned version aligned much better with the desired structure. This happened without the need for extra reward shaping—our rubric alone produced the right incentives.

Overall, the project highlights how even a compact model such as Gemma 3 1B can be pushed much further with the right reinforcement learning techniques, opening up possibilities for efficient, domain-specific reasoning systems that run on modest hardware.

<img width="573" height="281" alt="image" src="https://gist.github.com/user-attachments/assets/54e49842-7689-4c1c-92b9-bf31e45667ee" />


The complete methodology and experiments can be found [here](https://drive.google.com/file/d/1gcuPkPEQZoaO3seu8rHSo5AhmvbTESlq/view?usp=sharing). 


## Documentation

My journey through Gemma Garage has been documented in the following blog posts:

- [Gemma Garage Blogs #1](https://medium.com/@lucasfmartins/gemma-garage-blogs-1-a5a37e6ada61)
- [gemma Garage Blogs #2](https://medium.com/@lucasfmartins/gemma-garage-blogs-2-experimenting-with-grpo-and-prompt-optimization-cf29d43b0f5d)












