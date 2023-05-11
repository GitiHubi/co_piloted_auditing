# Artificial Intellence Co-Piloted Auditing

Welcome to the GitHub repository of the *Artificial Intelligence Co-Piloted Auditing* paper. This repository contains the prompt protocols used in our experiments on how auditors and foundation models work together to accomplish audit tasks.

## Paper Overview

Artificial Intelligence Co-Piloted Auditing represents a paradigm shift in the auditing profession. In this setup, the auditor collaboratively works with a foundation model, each contributing their unique strengths to the audit process. This approach combines the auditor's client-specific knowledge and professional judgement with the foundation model's capability to process large amounts of data and identify patterns.

The foundation model, trained on vast amounts of non-client specific exogenous data (e.g., financial news, financial reports, or satellite imagery), provides a broad knowledge base and multi-task capabilities. It processes large data sets, identifies patterns, and conducts initial assessments or projections, thereby supporting the auditor's decision-making process.

The auditor, on the other hand, utilizes client-specific endogenous data (e.g., journal entries, bank statements, or contracts) to provide contextual understanding, apply generally accepted audit principles, and exercise professional judgement. This in turn guides the foundation model's analysis and knowledge application.

## Repository Structure

This repository contains three distinct prompt protocols used in our experiments:

1. `Prompt_Protocol_A.md`: This ChatGPT protocol is designed for fine-tuning the GPT-4 model to conduct financial ratio analysis.
2. `Prompt_Protocol_B.md`: This OpenAI Playground protocol is intended for fine-tuning the GPT-4 model to perform a post-implementation review. 
3. `Prompt_Protocol_C.md`: This ChatGPT protocol is used for fine-tuniing the GPT-4 model to detect anomalies in journal entry data. 

Each protocol provides detailed instructions for the auditor to interact with the foundation model to accomplish a specific audit task.

## Usage

To use these protocols, simply follow the instructions provided in each file. They guide the interaction between the auditor and the foundation model, from task initiation to conclusion.

## Contributions

Your contributions and feedback are welcome! Please feel free to create an issue or submit a pull request.

## License

This project is licensed under the terms of the MIT license.

## Referencing This Work

If this project contributes to your research, or if you'd like to reference our work, please use the following citation:

H. Gu, M. Schreyer, K. Moffitt, and M.A. Vasarhelyi, *Artificial Intelligence Co-Piloted Auditing*, Social Science Research Network (SSRN), 2023.

For BibTeX users, you can cite this project as follows:

```bibtex
@misc{gu2023artificial,
  title={Artificial Intelligence Co-Piloted Auditing},
  author={Gu, H. and Schreyer, M. and Moffitt, K. and Vasarhelyi, M.A.},
  year={2023},
  howpublished={Social Science Research Network (SSRN)},
  note={Preprint},
  url={URL_of_the_Paper_on_SSRN}
}
