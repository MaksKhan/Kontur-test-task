# Kontur-test-task
Test assignment from an interview for a data scientist intern in Kontur

# Task description
The task was to select information from documents. There were two types of labels: 'обеспечение исполнение контракта' and 'обеспечение гарантийных обязательств'. In fact it was an extractive QA task. We had to find the answer in documents. However, sometimes there weren't answers it some texts and we had to mark it.

# EDA
Example of samples:

**Label (question)**: *"обеспечение исполнения контракта"*

**Extracted text (answer)**: *"Размер обеспечение исполнения контракта устанавливается от 0,5 % до 30 % начальной (максимальной) цены контракта"*

**Text (context)**: *I am sorry, I don't think you are interested in reading typical documents with* **2000+ symbols**


**Distribution was balanced**
![image](https://user-images.githubusercontent.com/72515541/233853764-f8e5ca54-4ba4-4c26-9921-4b80f1a2a1db.png)

**Most of texts without answer (empty texts) were of second class.**

![image](https://user-images.githubusercontent.com/72515541/233853713-bb6c1038-41b8-4fe1-9378-413a6bd41408.png)

**Most of empty texts were without word 'размер'** and most of texts with answers contained this worsd. 
![image](https://user-images.githubusercontent.com/72515541/233856001-5623bff6-9d8c-473d-b17d-63f214a36639.png)
**Adding this word to the labels improved score.**


# Model

***What have I tried?***

I have tried many models, trained only for russian or multilingual models which were trained on different datasets (I have even found some models trained on SberQuAD, special dataset for russian language)

***Which models were the best?***

In this case small models were better than large because all models were trained on datasets where answers usually no longer than 3-5 word or even shorter. However, answers in this task are much longer, that's why large models were hardly to learn on this data and small models were trained much more better and faster.

***What have I choosen?***

XLM-roberta was the best choise fot this task.

Hugging Face link: https://huggingface.co/deepset/xlm-roberta-base-squad2-distilled

# Result

✅ Acuracy on validation data is ~ 50%.
