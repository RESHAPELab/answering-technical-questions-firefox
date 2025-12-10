# A Comparison of Conversational Models and Humans in Answering Technical Questions: the Firefox Case

## Abstract 

The use of Large Language Models (LLMs) to support tasks in software development has steadily increased over recent years. From assisting developers in coding activities to providing conversational agents that answer newcomers’ questions. In collaboration with the Mozilla Foundation, this study evaluates the effectiveness of Retrieval-Augmented Generation (RAG) in assisting developers within the Mozilla Firefox project. We conducted an empirical analysis comparing responses from human developers, a standard GPT model, and a GPT model enhanced with RAG, using real queries from Mozilla’s developer chat rooms. To ensure a rigorous evaluation, Mozilla experts assessed the responses based on helpfulness, comprehensiveness, and conciseness. The results show that RAG-assisted responses were more comprehensive than human developers (62.50% to 54.17%) and almost as helpful (75.00% to 79.17%), suggesting RAG’s potential to enhance developer assistance. However, the RAG responses were not as concise and often verbose. The results show the potential to apply RAG-based tools to Open Source Software (OSS) to minimize the load on core maintainers without losing answer quality. Toning down retrieval mechanisms and making responses even shorter in the future would enhance developer assistance in massive projects like Mozilla Firefox.

## Study Design 
![View the embedded study design](https://github.com/RESHAPELab/answering-technical-questions-firefox/blob/main/documents/study_design_major.png?raw=true)

## Demographics

The study involved eight Mozilla Engineers who assessed the responses. Their demographics highlight a diverse range of experience levels and involvement in the Mozilla Firefox project:

| ID  | Confidence in Assessing Answers | Years of Professional Experience | Years Contributing to Mozilla | Gender       | Familiarity with Answering Questions in Matrix | Contribution to Supporting Newcomers |
|-----|--------------------------------|---------------------------------|------------------------------|--------------|-----------------------------------------------|--------------------------------------|
| D1  | 3                              | More than 10 years             | More than 10 years          | Male         | 5                                           | Occasional Bugzilla comments or Matrix discussion |
| D2  | 4                              | 4-7 years                      | 4-7 years                   | Not Provided | 5                                           | Creating good first bugs |
| D3  | 3                              | More than 10 years             | 1-3 years                   | Male         | 3                                           | Occasionally try to answer questions on Matrix, try to improve firefox-source-docs |
| D4  | 3                              | More than 10 years             | 1-3 years                   | Not Provided | 4                                           | Aside from helping new hires, I occasionally answer questions from newcomers on Matrix in general chat channels. |
| D5  | 4                              | More than 10 years             | More than 10 years          | Female       | 5                                           | I answer questions about the components I own in various channels. While I don't monitor the fast-moving #developers Matrix channel, I will reply there when pinged. |
| D6  | 5                              | 8-10 years                     | 4-7 years                   | Male         | 5                                           | Let's just say I read some of my answers in the quiz ;) |
| D7  | 3                              | More than 10 years             | More than 10 years          | Not Provided | 3                                           | In Discord (and Matrix but very rarely) |
| D8  | 4                              | More than 10 years             | 8-10 years                  | Male         | 5                                           | I tech lead projects and help onboard new users. I tend to work more closely with people on my team rather than broader general support like these Matrix questions are. I mentor folks often with 1:1s, chats, and more direct involvement. |

## Artifacts 

### Question Filtering process and Experts Evaluation 

We extracted ~77,900 messages, filtered 6,895 from 2024, and identified 229 as valid question-answer pairs. Two evaluators independently screened them, excluding those irrelevant, unclear, or not genuine. After resolving disagreements and a final review by a Firefox Expert, 52 high-quality questions (22.7%) were retained. The spreadsheets below show expert decisions on inclusion and exclusion. 

- [Question Filtering: Firefox Introduction Channel - PDF ](https://github.com/RESHAPELab/answering-technical-questions-firefox/blob/main/documents/question_filtering_firefox_introduction.pdf)
- [Question Filtering: Firefox Developers Channel - PDF](https://github.com/RESHAPELab/answering-technical-questions-firefox/blob/main/documents/question_filtering_firefox_developers.pdf)
- [Question Filtering: Firefox FrontEnd Channel - PDF](https://github.com/RESHAPELab/answering-technical-questions-firefox/blob/main/documents/question_filtering_firefox_front.pdf)

### Form for Questions Assessment

To provide insight into the evaluation process, we include an example of a completed assessment form by one of the Mozilla experts. This form illustrates how evaluators rated responses based on helpfulness, comprehensiveness, and conciseness, as well as their preferred response for practical use. Additionally, the expert provided open feedback, highlighting key strengths and weaknesses of the answers. This example helps demonstrate the structured methodology used to assess AI-generated and human responses in real-world technical discussions.

- [Form Example - PDF](https://github.com/RESHAPELab/answering-technical-questions-firefox/blob/main/documents/form_example.pdf)

### Final Questions 

We provide the complete dataset containing all 48 questions considered in this study. This file includes:

- **Evaluated Technical Questions**: The set of real-world queries collected from Mozilla's developer chat rooms.

- **Responses from Different Sources**:
  - Human responses (collected directly from Mozilla Firefox developers in Matrix chat rooms).
  - GPT responses (generated using GPT-4o).
  - GPT/RAG responses (generated using GPT-4o with retrieval-augmented contextual data).

- **Expert Evaluations**:
  - Mozilla engineers' assessments of responses based on:
    - **Helpfulness**
    - **Comprehensiveness**
    - **Conciseness**
  - The experts' preferred responses in practice.

- **Open comment**:
  - Strengths and weaknesses of answers source.


- [All Questions - PDF](https://github.com/RESHAPELab/answering-technical-questions-firefox/blob/main/documents/all_questions.pdf)


We also provide the subset containing the 4 questions assessed by all experts. The content in this file includes:

- **Overlapping Technical Questions**: The **four** real-world questions asked in Mozilla Firefox developer chat rooms.
- **Responses from Different Sources**:
  - **Human responses** (collected from Matrix chat discussions).
  - **GPT-generated responses** (generated using GPT-4o).
  - **RAG-enhanced responses** (generated using GPT-4o with retrieval-augmented contextual data).
- **Expert Evaluations**:
  - Mozilla engineers' ratings based on:
    - **Helpfulness**
    - **Comprehensiveness**
    - **Conciseness**
  - The experts' **preferred responses in practice**.
  - **Open comment**:
  - Strengths and weaknesses of answers source.
  
- **Inter-rater agreement analysis** using **Fleiss’ Kappa** to measure consistency across evaluators.

- [Overlapping Questions - PDF](https://github.com/RESHAPELab/answering-technical-questions-firefox/blob/main/documents/overlapping_questions.pdf)

### RAG

Below, we provide a spreadsheet listing all questions with their corresponding RAG-generated answers and the context retrieved by the Cognita Framework.

- [RAG - Questions and Context - PDF](https://github.com/RESHAPELab/answering-technical-questions-firefox/blob/main/documents/rag_context.pdf)
- [RAG - Questions and Context - CSV](https://github.com/RESHAPELab/answering-technical-questions-firefox/blob/main/documents/rag_context.csv)


## More Details
### Linguistic Metrics per Source

To better understand the linguistic characteristics of the responses, we computed a set of established metrics commonly used in natural language processing and readability analysis. These metrics capture aspects such as length, complexity, lexical richness, and writing style. The table below summarizes the results for each source type.


| Source | Word Count | Sentence Count | Avg. Sentence Length | Flesch-Kincaid | Dale-Chall | Gunning Fog | TTR  | Lexical Density | Adverb Density |
|--------|------------|----------------|-----------------------|----------------|------------|--------------|------|------------------|----------------|
| Human  | 33.73      | 1.71           | 21.90                 | 12.65          | 9.62       | 11.21        | 0.88 | 0.54             | 0.09           |
| GPT    | 60.96      | 2.33           | 27.25                 | 12.86          | 11.37      | 15.00        | 0.74 | 0.51             | 0.03           |
| RAG    | 79.83      | 3.21           | 26.40                 | 11.80          | 11.15      | 13.96        | 0.70 | 0.52             | 0.03           |

---


| Metric              | Description |
|---------------------|-------------|
| **Word Count**      | Total number of words in the response. Indicates verbosity. |
| **Sentence Count**  | Number of sentences. Often linked to structural complexity. |
| **Avg. Sentence Length** | Average number of words per sentence. Higher values may indicate more complex syntax. |
| **Flesch-Kincaid**  | A readability score estimating U.S. school grade level needed to understand the text. Higher values = more complex. |
| **Dale-Chall**      | Readability metric that penalizes use of difficult or uncommon words. Higher = harder to read. |
| **Gunning Fog**     | Estimates years of formal education needed to understand the text. Values above 12 suggest complex writing. |
| **TTR (Type-Token Ratio)** | Lexical diversity, i.e., unique words divided by total words. Higher = more varied vocabulary. |
| **Lexical Density** | Ratio of content words (nouns, verbs, adjectives, adverbs) to total words. Indicates information richness. |
| **Adverb Density**  | Proportion of adverbs to total words. May relate to stylistic verbosity or qualification. |
