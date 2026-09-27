# 🛠️ Equipment SME Assistant

An AI-powered Equipment Subject Matter Expert (SME) Assistant built using **AWS serverless services and Amazon Bedrock**. The application allows equipment specialists to submit natural-language questions and receive AI-generated responses through a secure API-driven architecture.

The project demonstrates how **Amazon Bedrock, AWS Lambda, API Gateway, Streamlit, CloudWatch, and Bedrock Guardrails** can be combined to build a production-oriented Generative AI application.

---

## 📌 Project Overview

Equipment specialists often need quick access to technical information when troubleshooting equipment or looking for guidance. Searching through large amounts of documentation can be time-consuming.

The **Equipment SME Assistant** provides a conversational interface where users can submit questions or prompts related to equipment. The request is processed through an AWS serverless architecture and sent to an Amazon Bedrock foundation model to generate a response.

### Example

```text
Equipment SME
      │
      │ User Prompt
      ▼
AWS API Gateway
      │
      │ API Request
      ▼
AWS Lambda
      │
      │ Model Invocation
      ▼
Amazon Bedrock
      │
      │ AI Response
      ▼
AWS Lambda
      │
      ▼
API Gateway
      │
      ▼
Streamlit Application

Application
🏗️ Architecture

The core architecture consists of:

Streamlit – User-facing application interface
Amazon API Gateway – Secure API entry point
AWS Lambda – Serverless compute and request processing
Amazon Bedrock – Foundation model access and AI inference
Amazon CloudWatch – Logging, monitoring and observability
Amazon Bedrock Guardrails – Responsible AI and content control
Architecture Flow
┌──────────────────────┐
│   Equipment SME      │
│      / User          │
└──────────┬───────────┘
           │
           │ User Prompt
           ▼
┌──────────────────────┐
│   Streamlit UI       │
└──────────┬───────────┘
           │
           │ HTTP Request
           ▼
┌──────────────────────┐
│   API Gateway        │
└──────────┬───────────┘
           │
           │ API Event
           ▼
┌──────────────────────┐
│   AWS Lambda         │
│                      │
│ Request Processing   │
│ Prompt Construction  │
│ Bedrock Invocation   │
└──────────┬───────────┘
           │
           │ Prompt
           ▼
┌──────────────────────┐
│   Amazon Bedrock     │
│                      │
│ Foundation Model     │
└──────────┬───────────┘
           │
           │ AI Response
           ▼
┌──────────────────────┐
│   AWS Lambda         │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│   Streamlit UI       │
└──────────────────────┘

       ┌──────────────────┐
       │  CloudWatch      │
       │ Logs & Metrics   │
       └──────────────────┘

       ┌──────────────────┐
       │ Bedrock          │
       │ Guardrails       │
       └──────────────────┘

**Features:**
Accepts a question from the user.
Sends the request through an API Gateway endpoint.
AWS Lambda processes the incoming API event.
Lambda constructs the prompt using the user request and system instructions.
Amazon Bedrock invokes a selected foundation model.
The generated response is returned through Lambda.
API Gateway delivers the response to the application.
Streamlit displays the response to the user.
CloudWatch provides logging and monitoring.
Bedrock Guardrails can be used to apply responsible-AI controls.
