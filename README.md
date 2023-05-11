# Artificial Intelligence Co-Piloted Auditing

🚀 Welcome to the official GitHub repository for the [Artificial Intelligence Co-Piloted Auditing](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4444763) research. This project is a collaboration 🤝 between the [Accounting Research Center at Rutgers University](http://raw.rutgers.edu) and the [Institute of Computer Science at the University of St. Gallen](https://www.ics.unisg.ch/). 

This repository maintains the prompt protocols implemented in our experiments, demonstrating the collaborative auditing tasks accomplished by auditors 👩‍💼👨‍💼 and artificial intelligence 🧠 foundation models. Join us 🙋‍♀️🙋‍♂️ as we explore the limitless possibilities 🌌 of combining human expertise with AI potential in auditing. The latest version of the paper can be obtained from SSRN via the following links: [Abstract](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4444763), [PDF](https://papers.ssrn.com/sol3/Delivery.cfm/SSRN_ID4444763_code5066211.pdf?abstractid=4444763&mirid=1).

## About the Paper

<p align="left">
  <img src="./assets/vis_001_copiloted_auditing.png" alt="Co-Piloted Auditing" width="700">
  <br>
  <i>Figure: Co-piloted auditing, wherein human auditors collaborate with foundation AI models to accomplish audit tasks.</i>
</p>

In this study, we propose the concept of artificial intelligence co-piloted auditing, emphasizing the collaborative potential of auditors and [foundation models](https://www.economist.com/interactive/briefing/2022/06/11/huge-foundation-models-are-turbo-charging-ai-progress), such as [LaMDA](https://blog.google/technology/ai/lamda/), [DALL-E](https://openai.com/product/dall-e-2), [PaLM](https://ai.googleblog.com/2022/04/pathways-language-model-palm-scaling-to.html), and [GPT-4](https://openai.com/research/gpt-4), in the auditing domain. We imagine an audit setup where human auditors' capabilities are enhanced through artificial intelligence, facilitating optimal outcomes across a variety of audit tasks:

- The **human auditor**, conversely, applies professional judgment and a deep understanding of client-specific endogenous data (*e.g.,* journal entries, bank statements, contracts) for contextual interpretation and application of widely accepted audit principles, thereby guiding the foundation model's analysis and knowledge application.

- The **foundation model**, with its proficiency in handling extensive non-client specific exogenous data (*e.g.,* financial news, financial reports, satellite imagery), offers a broad knowledge base and multi-tasking capabilities. It discerns patterns, conducts preliminary assessments or projections from large data sets, thereby enriching the auditor's decision-making process.

In this overarching co-pilot setup, the auditor and the foundation model do not merely act as users and tools; **they are collaboratively navigating the audit together in continuous and iterative dialogue**. To exemplify the potential of this co-piloted audit paradigm, we illustrate a systematic fine-tuning approach of foundation models using chain-of-thought prompting that enables instruction learning, in-context learning, and sequential reasoning. We demonstrate the potential of co-piloted auditing, by fine-tuning GPT-4 using OpenAI's ChatGPT interface towards three different audit tasks namely financial ratio analysis, text mining, and journal entry testing. 

This work reflects early work-in-progress. We warmly welcome contributions and feedback! Feel free to suggest your own prompt protocols, raise issues, or submit pull requests. The authors are responsible for the content creation, while OpenAI's [GPT-4](https://openai.com/research/gpt-4) ([ChatGPT](https://chat.openai.com)) has been employed in the proofreading.

## Repository Structure

We provide a detailed description of the formulated prompt protocols and the corresponding responses generated by ChatGPT, ensuring reproducibility. This repository encompasses three distinct prompt protocols used in our experiments:

1. **Experiment A:** Fine-tuning protocol for the GPT-4 model, targeting financial ratio analysis ([`Prompt_Protocol_A.md`](./protocols/Prompt_Protocol_A.md)).
2. **Experiment B:** Fine-tuning protocol for the GPT-4 model, focusing on post-implementation review ([`Prompt_Protocol_B.md`](./protocols/Prompt_Protocol_B.md)).
3. **Experiment C:** Fine-tuning protocol for the GPT-4 model, aiming at journal entry testing ([`Prompt_Protocol_C.md`](./protocols/Prompt_Protocol_C.md)).


Each protocol presents comprehensive instructions for auditors to interact with the foundation model, guiding the ChatGPT interaction from task initiation to completion. We envision this work as an initial step towards the widespread implementation of co-piloted auditing, paving the way for more efficient, accurate, and insightful audit procedures.

## Protocol Usage

To make the most out of these protocols 🚀, simply follow the 📝 instructions detailed in each file. They've been designed to guide you 🧭 through the interaction process with OpenAI's [GPT-4](https://openai.com/research/gpt-4) foundation model 🤖 using [ChatGPT](https://chat.openai.com) 💬. Dive in and let the AI collaboration begin!

## Citing This Work

If our work contributes to your research, or you find it worthy of citation, please use:

Gu, H., Schreyer, M., Moffitt, K., & Vasarhelyi, M.A. 2023. ***Artificial Intelligence Co-Piloted Auditing***. Social Science Research Network (SSRN).

For BibTeX users:

```bibtex
@misc{gu2023artificial,
  title={Artificial Intelligence Co-Piloted Auditing},
  author={Gu, H. and Schreyer, M. and Moffitt, K. and Vasarhelyi, M.A.},
  year={2023},
  howpublished={Social Science Research Network (SSRN)},
  note={Preprint},
  url={https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4444763}
}
```

## License

This project is licensed under the terms of the MIT license. See the [LICENSE](LICENSE) file for details.
