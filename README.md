# Detecting Attitude in UNSC speeches with Large Language Models (LLMs)



## Project Description

This project investigated if _Large Language Models (LLMs)_ were able to detect appraisals, particularly _attitude_, in diplomatic speeches, specifically in the _UNSC_ dataset (Schönefeld et al., 2019). To carry out this investigation, we performed several tasks including a manual annotation of a sample of 87 _UNSC_ speeches with _attitude_ labels (_affect_, _appreciation_ and _judgement_), from the _Appraisal Theory_ (Martin and White, 2005; Oteiza, 2017; Anisimova, 2023) and different experiments with various LLMs (i.e., BERT, BART, T5 and Sentence Transformers). The experiments were carried out in three phases: 
* **Phase I:**  multi-class classification of annotated fragments. 
* **Phase II:** binary classification of _Elementary Discourse Units (EDUs)_ with _appraisal_ labels (yes when appraisal was present and no when it was not). 
* **Phase III:**  multi-class classification of _EDUs_ with _attitude_ labels.  <br />

In addition, an analysis of the misclassified labels by the best three performing models and a comparative analysis between the results obtained by Zaczynska et al. (2024) with _Lexicoder Sentiment Dictionary_ (Young and Soroka, 2012) and our annotations were carried out. 

## General Organization 

This repository repository includes the dataset used, the results and the code. 

1) **Code:** includes the different python codes developed for this project: 
* **Models:** includes the codes for the different Large Language Models: <br />
    - _BART_text_classification.ipynb:_ code for binary and multi-class classification with BART. <br />
    - _Flan_T5_QA_for_Text_Classification.ipynb:_ code for binary and multi-class classification with Google-Flan-T5 model with prompt. <br />
    - _Flan_T5_Zero_Shot_Classification.ipynb:_ code for binary and multi-class classification with Google-Flan-T5 with zero shot classification. <br />
    - _ST_for_Binary_Classification.ipynb:_ code for binary classification with sentence transformers (BART, BERT, RoBERTa and T5).<br />
    - _ST_for_Multi_Class_Classification.ipynb:_ code for multi-class classification with sentence transformers (BART, BERT, RoBERTa and T5).<br />
* _Lexicoder_vs_annotations.ipynb:_ includes code used to compare Lexicoder results (Zaczynska et al., 2024)  with the sample of annotated speeches with attitude. 
* **requirements.txt:** contains all requirements for the code.

2) **Data:** includes the data files used with for experiments. 
* **Experiments Data:** includes the following data samples: <br />
    - _Edus+Annotations_data.xlsx:_ data sample including all annotated fragments and _EDUs_ with or without appraisal. Dataset for binary classification. <br />
    - _Edus+Annotations_Only_Yes_Appraisal_Data_withoutDuplicates.xlsx:_ data sample including all annotated fragments and _EDUs_ with attitude. Dataset for muli-class classification. <br />
    - _data_for_few_shot_training_SetFit.xlsx:_ includes the sample of examples obtained from Anisimova's (2023) guidelines for few shot training of sentence transformers. <br />
* _anno_VS_lexicoder_Manually_checked.xlsx:_ includes the manually analyzed sample of results obtained by comparing Lexicoder's results (Zaczynska et al., 2024)  and annotated sample.

3) **Results:** includes the different results obtained with this project: 
* **Error Analysis:** includes the following files:  <br />
    - _Appraisal_Linguistic_Analysis_Patterns.xlsx:_ sample of analyzed examples for determining linguisitc patterns. <br />
    - _Error_Analysis_Examples.xlsx:_ sample of misclassified labels for best performing models. <br />
* **Results Appraisal:** includes the following files:  <br />
    - _Results_Appraisal_LlMs.xlsx:_  binary classification predictions obtained with BART, Flan-T5 with prompting and Flan-T5 zero shot classification. <br />
    - _Results_Appraisal_Sent-Trans.xlsx:_ binary classification predictions obtained with sentence transformers (BERT, BART, RoBERTa and T5). <br />
* **Results Attitude:** includes the following files:  <br />
    - _Results_Attitude_LlMs.xlsx:_  multi-class classification predictions obtained with BART, Flan-T5 with prompting and Flan-T5 zero shot classification. <br />
    - _Results_Attitude_Sent-Trans.xlsx:_ multi-class classification predictions obtained with sentence transformers (BERT, BART, RoBERTa and T5). <br />
* **Visualizations:** includes the visualizations (confusion matrices and plots):  <br />
    - **Appraisal:** includes confusion matrices for binary classification for all models (Flan-T5 with promting, Flan-T5-ZSC, BART and sentence transformers (BERT, BART, RoBERTa and T5)). <br />
    - **Attitude:** includes confusion matrices for multi-class classification for all models (Flan-T5 with promting, Flan-T5-ZSC, BART and sentence transformers (BERT, BART, RoBERTa and T5)).<br />
    - _dist_edus_after.png:_ plot with distribution of attitude labels in sample after removing duplicates. <br />
    - _dist_edus_before.png:_ plot with distribution of attitude labels in sample before removing duplicates. <br />
 
4) IM_Final_Report_Valentina_Tretti.pdf: includes the final report. 

## Author 

Valentina Tretti 

## References 
Anisimova, M. (2023). Argumentation in speeches of the security council of the united nations organizations: Annotation manual for defining attitudes. Unpublished manuscript.

Martin, J.R. and White, P. (2005). The Language of Evaluation: Appraisal in English. 

Oteíza, T. (2017).The appraisal framework and discourse analysis. In T. Bartlett and G. O’Grady, editors, The Routledge Handbook of Systemic Functional Linguistics, pages 457–472. Routledge, London

Schönfeld, M.,  Eckhard, S.,  Patz, R. and Meegdenburg, H. (2019). The un security council debates. Harvard Dataverse, V5.

Young, L. and Soroka, S. (2012). Affective news: The automated coding of sentiment in political texts. Political Communication, 29(2):205–231.

Zaczynska, K., Bourgonje, P. and Stede, M. (2024). How Diplomats Dispute: The UN Security Council Conflict Corpus. In Proceedings of the Joint International Conference on Computational Linguistics, Language Resources and Evaluation (LREC-COLING 2024), Turin, Italy. To appear

