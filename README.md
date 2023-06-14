# EUInstruct
<p align="center">
  <img height="150" src="https://upload.wikimedia.org/wikipedia/commons/thumb/b/b7/Flag_of_Europe.svg/320px-Flag_of_Europe.svg.png">
</p>

EUInstruct is a repository of instruction dataset in (non-English) European languages to finetune LLMs.

Following the release of LLama in February 2023, there has been a swift development of instruction datasets to fine-tune LLMs for conversational uses or on specific tasks. Yet theses dataset are largely focused on English and to a lesser extent on Chinese. 

This project strives to compile the available instruction dataset for European languages, in the spirit of supporting a wider multilingual ecosystem of open source LLMs. This include two major collections:
* Original instructions in 28 European languages identified through lang_detect.
* Translated instructions in a smaller selections of European languages.

As a caveat, **instructions are not yet deduplicated**. Since we have merged different sources, redundancies are likely. We will proceed to create a deduplicated version once we have finished collecting all the main sources.

## Structure
All the original datasets have been normalized following the established structure of Alpaca-style datasets (instruction, output and, when available, input). The files are structured by languages rather than provenance. EUinstruct can consequently be used to train a language-specific LLM or a multilingual LLM when relevant. For instance a "Swiss LLM" could cross the German-speaking, French-speaking and Italian-speaking dataset.

The provenance of each instruction is integrated at the data level with a "source" attribute. This makes it easy to filter in or out some dataset. Additionally, each instruction has a unique ID that is either the original one from the dataset or, by default, the ordering id. A sample of italian-speaking instruction is structured this way:

```json
{
"source": "openassistant",
"language": "it", 
"instruction_id": "a103ec1c-7844-46b1-9f1b-1d8bc1ae49a7", 
"instruction": "Spiegami come funziona un modello GPT, considerando che di deep learning ne capisco poco", 
"output": "Un modello GPT (Generative Pre-trained Transformer) è un tipo di modello di deep learning che è stato addestrato su grandi quantità di testo in modo da essere in grado di generare testo in modo autonomo. Questi modelli sono basati su una architettura Transformer, che è stata progettata per gestire le relazioni tra parole in una frase.\n\nIn sintesi, un modello GPT funziona analizzando una grande quantità di testo e cercando di capire le relazioni tra le parole. Questo gli permette di prevedere la prossima parola in una frase in base alle parole che lo precedono. Quando viene addestrato su un grande corpus di testo, un modello GPT impara a generare testo coerente e plausibile in base alle relazioni tra le parole che ha visto durante l'addestramento.\n\nPer comprendere meglio come funziona un modello GPT, puoi immaginarlo come un bambino che impara a scrivere frasi guardando molte frasi scritte da altre persone. Il bambino impara a capire le relazioni tra le parole e le regole grammaticali e può quindi generare frasi coerenti e plausibili. Allo stesso modo, un modello GPT impara a capire le relazioni tra le parole e le regole grammaticali guardando molte frasi scritte da altre persone (cioè, il corpus di testo su cui è stato addestrato)."
}
```

## Original instructions

This directory compiles the available non-English and non-Chinese instructions in the leading multilingual datasets:
* Guanaco
* ShareGPT
* OpenAssistant
* [Flan-v2 (100k resampled)](https://beaker.org/api/v3/datasets/01GZTTS2EJFPA83PXS4FQCS1SA/files/flan_v2_resampled_100k.jsonl)
* [Self-Instruct](https://github.com/yizhongw/self-instruct)
* [Stack-Exchange-Paired](https://huggingface.co/datasets/lvwerra/stack-exchange-paired) (heavily filtered as language detection is harmed by the high prevalence of math/programing content)

## Translated instructions
This directory includes versions of English-speaking datasets that have been automatically translated. This include mostly Alpaca.

When available these datasets are both larger and both comprehensive. Yet, they will obviously not include cultural topics specific to the language and may miss out on important nuances and language varieties. Some instructions can also be wrong as they rely on meta-analysis of the language itself (grammatical correction for instance).

The main sources of translations are:
* [Vicogne](https://github.com/bofenghuang/vigogne) for French (Alpaca, ShareGPT and additional sources…)
* [Stambecco](https://github.com/mchl-labs/stambecco) for Italian (Alpaca)
* [Zicklein](https://github.com/avocardio/zicklein) for German (Alpaca)
* [ArmandDS](https://github.com/ArmandDS/blog-post/tree/main/NLP/LLM-ALPACA-SPANISH) for Spanish (Alpaca)
