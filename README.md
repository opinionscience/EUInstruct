# EUInstruct
EUInstruct is a repository of instruction dataset in (non-English) European languages to finetune LLMs.

Following the release of LLama in February 2023, there has been a swift development of instruction datasets to fine-tune LLMs for conversational uses or on specific tasks. Yet theses dataset are largely focused on English and to a lesser extent on Chinese. This project compiles all the available instruction dataset for European languages, with a primary focus on original language content rather than automated translation. It aims to support a wider multilingual ecosystem of open source LLMs.

All datasets are ordered by languages and follow the established structure of Alpaca-style datasets (instruction-input-output). EUinstruct can consequently be used to train a language-specific LLM or a multilingual LLM when relevant. For instance a "central european LLM" could cross the Czech, Hungarian, Slovakian and Romanian dataset.

The provenance of each instruction is integrated at the data level with a "source" attribute. This makes it easy to filter in or out some dataset. Additionally, each instruction has a unique ID that is either the original one from the dataset or, by default, the ordering id.
