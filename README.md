# EUInstruct
EUInstruct is a repository of instruction dataset in (non-English) European languages to finetune LLMs.

Following the release of LLama in February 2023, there has been a swift development of instruction datasets to fine-tune LLMs for conversational uses or on specific tasks. Yet theses dataset are largely focused on English and to a lesser extent on Chinese. 

This project strives to compile all the available instruction dataset for European languages. It aims to support a wider multilingual ecosystem of open source LLMs. This include two major collections:
* Original instructions in 28 European languages.
* Translated instructions in a smaller selections of European languages.

All datasets are ordered by languages and follow the established structure of Alpaca-style datasets (instruction-input-output). EUinstruct can consequently be used to train a language-specific LLM or a multilingual LLM when relevant. For instance a "Swiss LLM" could cross the German-speaking, French-speaking and Italian-speaking dataset.

The provenance of each instruction is integrated at the data level with a "source" attribute. This makes it easy to filter in or out some dataset. Additionally, each instruction has a unique ID that is either the original one from the dataset or, by default, the ordering id. A sample of italian-speaking instruction is structured this way:

```json
{"source": "openassistant", "language": "it", "instruction_id": "a103ec1c-7844-46b1-9f1b-1d8bc1ae49a7", "instruction": "Spiegami come funziona un modello GPT, considerando che di deep learning ne capisco poco", "output": "Un modello GPT (Generative Pre-trained Transformer) è un tipo di modello di deep learning che è stato addestrato su grandi quantità di testo in modo da essere in grado di generare testo in modo autonomo. Questi modelli sono basati su una architettura Transformer, che è stata progettata per gestire le relazioni tra parole in una frase.\n\nIn sintesi, un modello GPT funziona analizzando una grande quantità di testo e cercando di capire le relazioni tra le parole. Questo gli permette di prevedere la prossima parola in una frase in base alle parole che lo precedono. Quando viene addestrato su un grande corpus di testo, un modello GPT impara a generare testo coerente e plausibile in base alle relazioni tra le parole che ha visto durante l'addestramento.\n\nPer comprendere meglio come funziona un modello GPT, puoi immaginarlo come un bambino che impara a scrivere frasi guardando molte frasi scritte da altre persone. Il bambino impara a capire le relazioni tra le parole e le regole grammaticali e può quindi generare frasi coerenti e plausibili. Allo stesso modo, un modello GPT impara a capire le relazioni tra le parole e le regole grammaticali guardando molte frasi scritte da altre persone (cioè, il corpus di testo su cui è stato addestrato)."}
```
