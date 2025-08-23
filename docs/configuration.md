---
title: Developer Guide 
nav_order: 2
---

# Developer Guide 
{: .no_toc }

{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---


## Tools
This bug localizer requires some tools for static analysis. Please be sure to download the following tools before you deploy it.

- [**Joern**](https://docs.joern.io/): We use Joern for data flow analysis and methods extractions.

- [**Doxygen**](https://www.doxygen.nl/): We use Doxygen to generate the callgraph.

## LLM Agents
Due to the limit of the input size in LLMs, we cannot keep using one LLM for the entire task. To this end, we seperate our LLMs agents into three differnt categories:

- **Mehtod and file exploration**: Explore the related file path and methods from bug report
- **Static analysis**: Decide whether to use static analysis or callgraph analysis 
- **Bug reasoning**: Reason the localization of the bugs and summarize the bug reasoning

## Workflow

![work flow](/assets/images/workflow.png) 

## Pre-requisite
To set up your local environment, run the following command. We recommend the use of a virtual environment for running the experiments.

```bash
pip install -r requirements.txt
```

## Configurations

Please create the JSON file with the following format to set up your configuration. Note that we do not upload this file for the security reason. For password, you will need to generate the APP password instead of the password for your email.

```json
{
  "doxyfile_dir":"your doxyfile directory",
  "model_name": "o4-mini-2025-04-16",
  "joern_dir": "Joern directory",
  "openai_key": "file name of your OpenAI key",
  "sender_email":"your email",
  "sender_password":"Your password"
}
```

We used ```o4-mini-2025-04-16``` for the experiments although you could try different cheaper/better models. Please refer to [OpenAI](https://platform.openai.com/docs/models) for more information.

{: .warning }
There are some string parsing might fail when you change to different models because different models could have output with different formats. Be sure to check this, when you use different models.

## Quick Start
To run the application, you can simply run the following command.

```bash
python3 app.py
```

After you start, you will be able to open the website on your browser in http://127.0.0.1:5000/

