# Artificial Intelligence Co-Piloted Auditing

Welcome to the official GitHub repository for the *Artificial Intelligence Co-Piloted Auditing* research paper. This repository maintains the prompt protocols implemented in our experiments, demonstrating the collaborative auditing tasks accomplished by auditors and foundation models.

## About the Paper

<p align="left">
  <img src="./assets/vis_001_copiloted_auditing.png" alt="Co-Piloted Auditing" width="500">
  <br>
  <i>Figure: Co-piloted auditing, wherein human auditors collaborate with foundation AI models to accomplish audit tasks.</i>
</p>

In this paper we explore a new paradigm in the auditing profession, where auditors and foundation models collaborate, leveraging their distinct strengths:

- The foundation model, with its proficiency in handling extensive non-client specific exogenous data (*e.g.,* financial news, financial reports, satellite imagery), offers a broad knowledge base and multi-tasking capabilities. It discerns patterns, conducts preliminary assessments or projections from large data sets, thereby enriching the auditor's decision-making process.

- The auditor, conversely, applies professional judgment and a deep understanding of client-specific endogenous data (*e.g.,* journal entries, bank statements, contracts) for contextual interpretation and application of widely accepted audit principles, thereby guiding the foundation model's analysis and knowledge application.

In this overarching co-pilot setup, the auditor and the foundation model do not merely act as users and tools; they are collaboratively navigating the audit together in continuous and iterative dialogue.

This work reflects early work-in-progress. We very much welcome feedback and comments. The authors are responsible for the content creation, while GPT-4 (ChatGPT) has been employed in the proofreading.

## Repository Structure

This repository encompasses three distinct prompt protocols used in our experiments:

1. `Prompt_Protocol_A.md`: Fine-tuning protocol for the GPT-4 model, targeting financial ratio analysis.
2. `Prompt_Protocol_B.md`: Fine-tuning protocol for the GPT-4 model, focusing on post-implementation review.
3. `Prompt_Protocol_C.md`: Fine-tuning protocol for the GPT-4 model, aiming at detecting anomalies in journal entry data.

Each protocol presents comprehensive instructions for auditors to interact with the foundation model, guiding the ChatGPT interaction from task initiation to completion.

## Usage

To utilize these protocols, follow the instructions detailed in each file. They have been designed to guide you through the interaction process with OpenAI's GPT-4 foundation model.

## Contributions

We warmly welcome your contributions and feedback! Feel free to suggest your own prompt protocols, raise issues, or submit pull requests.

## License

This project is licensed under the terms of the MIT license.

## Citing This Work

If our work contributes to your research, or you find it worthy of citation, please use:

H. Gu, M. Schreyer, K. Moffitt, and M.A. Vasarhelyi, *Artificial Intelligence Co-Piloted Auditing*, Social Science Research Network (SSRN), 2023.

For BibTeX users:

```bibtex
@misc{gu2023artificial,
  title={Artificial Intelligence Co-Piloted Auditing},
  author={Gu, H. and Schreyer, M. and Moffitt, K. and Vasarhelyi, M.A.},
  year={2023},
  howpublished={Social Science Research Network (SSRN)},
  note={Preprint},
  url={URL_of_the_Paper_on_SSRN}
}
