---
title: Prompt Format
nav_order: 3
---

# Prompt Format
{: .no_toc }

{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Information Collection
We used the following prompt form for information collection LLMs, where \{bug\_report\} is the bug report and \{filename\} is filenames of source code files.
```
Given the bug report {bug_report}, can you tell me which methods and files 
would you look at based on the bug report. Please use the format: METHOD:
\n1.\nFILE:\n1.\n. Please do not make up anything and just provide me 
the name of the methods and the name of the files without any explanation. 
Please only find three most important methods/files and please do not 
include () or any other information in the method name. The file should 
be in {filename}. Please be sure to reason the method name or file 
path based on the bug report and do not make up any method name as your job is 
to look at the bug report and find the related methods only. Note that 
you do not need to provide the file if you do not see the file. In this case, 
you can just say METHOD:\n1.FILE:1.NONE If you provide the file, please 
follow the provided file path. If you do not know the name of the method, please 
just give me the file name. In this case, you just need to give me METHOD:\n1.NONE\nFILE:\n1.\n.
```

## Static Analysis
We used the following prompt for deciding which static analysis to use, where \{bug\_report\} is the bug report from the user, \{codeblocks\} is the source code of the entry point, and \{function\_name\} is the name of the entry point functions.
```
Now you can use call graph analysis, a method to analyze how the methods call 
each other and data flow analysis, a method to analyze how data flow in the 
problem. Given the bug report {bug_report} and the related methods 
{codeblocks}, could you tell me which method would you use to analyze the bugs? 
Please just tell me what you would use and be sure to refer to the context and 
not make up anything yourself. Please use the template: data flow
analysis:\tsource:\tsink:\t if you think data flow analysis is an appropriate 
method. Please note that source should be the name of the method in 
{function_name} and sink should be in the a function that is 
inside the same method (if this is not the case, please suggest call graph) 
and do not provide any other information and the example is data 
flow analysis:\tsource:\ta\nsink:\tb\n where a is the
method name and b is the function name. otherwise:  call graph analysis
```


In addition, we used the following prompt for selecting the call chain, where \{callpath\} is the callgraph path from the tool.

```
Now, can you look at the call path {callpaths} and tell me which one do 
you need to locate the bugs based on the bug report {bug_report} and related 
methods {codeblocks}. Please give me the complete paths as shown in call path 
with the template path:\n1.\t The between method sign is "<-" or "->". Please 
only tell me the paths that help to localize the bugs and the call chain should 
be in the provided paths and please only provide the call chain without any 
explanation. Please follow the call chain that I give you. Do not 
have () in the call chain.
```


## Bug Reasoner
We used the following format as the prompt if callgraph analysis is used and the similar template for dataflow analysis, where \{callmethods\} is the functions in the callgraph and \{path\_to\_explore\} is the call chains.

```
The strategies to localize the bugs are forward reasoning, backward 
reasoning, and code comprehension. Give you the related methods 
{codeblocks} and methods in call graph {callmethods}, and the call chain 
{path_to_explore}, could you use one of the strategies to reason the bugs 
and localize the bugs based on bug report {bug_report}? Please do not 
assume any information that is not provided, any information not in call 
chain and related methods, the code snippets not in the provided code, 
and the name of the method. You should only look at the provided method 
to reason the bugs. If the methods that you need are not in the call 
chain or related methods, you can request the methods. Please remember to
choose either forward reasoning, backward reasoning or code comprehension
to reason where the bugs localize and keep it consistence with the 
previous reasoning methods if you have and do not generate new code 
snippet or new call chain for the specific methods as your task is not to
generate anything. Instead, your task is only to localize the bugs. 
Please use the template REASONING METHODS:\t\nREASONING 
STEPS:\t\nHypothesis:\t\nMETHOD MISSING:\t\nMETHOD MISSING:\t\n(if you 
have multiple methods and please only provide method name and no other 
information is needed). Please do not make up any method name. Please 
follow the call chain. Otherwise, use REASONING METHODS:\t\nREASONING 
STEPS:\t\nHypothesis:\t\n. Please do not make up anything outside the 
provided information, but you can request it if needed. The reasoning 
method should be the same as the previous one if you have already chose 
one and you should follow the call chain and please make your reasoning 
steps specific and do not make up any method name.
```




