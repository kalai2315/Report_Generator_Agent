
##Topic Report Generator using LangChain

This project implements a simple report generator that produces a structured report for any given topic. It generates a short description, lists pros and cons in bullet points, and merges everything into a well-formatted summary.

**Overview**

The application uses LangChain Expression Language (LCEL) to:

Generate a two-line description

Generate three pros

Generate three cons

Merge all of the above into a final topic report

**Components**

**1. Prompt Chains**
   
description_chain: Generates a brief two-line description of the topic.

pros_chain: Lists three bullet-point pros for the topic.

cons_chain: Lists three bullet-point cons for the topic.

Each chain is created using ChatPromptTemplate, an LLM (such as Gemini), and a StrOutputParser.

**2. RunnableParallel Branch**

This runs all three chains in parallel, pulling "topic" from input and producing keys: description, pros, and cons.

**3. Merge Chain**

Merges the generated content using a structured prompt template.

The final output includes:

Topic

Description

Pros and Cons section


**Requirements**

Python 3.8+

langchain

An LLM like Gemini via langchain-google-genai or OpenAI via langchain-openai
