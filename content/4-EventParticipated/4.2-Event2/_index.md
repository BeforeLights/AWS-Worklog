---
title: "Event 2"
date: "2025-11-15"
weight: 02
chapter: false
pre: " <b> 4.2. </b> "
---

# Summary Report: “AWS Cloud Mastery Series #1 - AI/ML/GenAI on AWS”

### Event Objectives

The event aimed to provide a comprehensive introduction to the capabilities of AI, Machine Learning (ML), and Generative AI (GenAI) on AWS. Specific objectives included:

- Exploring the foundational concepts of Generative AI and its applications.
- Demonstrating the use of AWS services and tools for AI/ML workflows.
- Highlighting best practices for integrating AI/ML into production environments.

### Speakers

The event featured a diverse panel of experienced professionals who shared their expertise:

- **Lam Tuan Kiet** – Senior DevOps Engineer, FPT Software
- **Danh Hoang Hieu Nghi** – AI Engineer, Renova Cloud
- **Dinh Le Hoang Anh** – Cloud Engineer Trainee, First Cloud AI Journey
- **Van Hoang Kha** – Cloud Security Engineer, AWS Community Builder

### Key Highlights

#### Generative AI with Amazon Bedrock

The session provided an in-depth exploration of Amazon Bedrock, a fully managed service for deploying and scaling foundation models. Key topics included:

- **Foundation Models:** Unlike traditional models, foundation models are pre-trained on vast datasets and can be adapted for a wide range of tasks. Amazon Bedrock offers models from leading AI companies such as OpenAI, Anthropic, and Cohere.

- **Prompt Engineering:** Techniques for crafting effective prompts to optimize model responses:
  - **Zero-Shot Prompting:** Providing no prior context or examples.
  - **Few-Shot Prompting:** Including a few examples to guide the model.
  - **Chain of Thought (CoT):** Incorporating reasoning steps to improve the quality of responses.

- **Retrieval Augmented Generation (RAG):** A technique to enhance model responses by retrieving relevant information from external data sources:
  - **Retrieval:** Fetching relevant data from a knowledge base.
  - **Augmentation:** Adding the retrieved data as context to the prompt.
  - **Generation:** Producing responses based on the augmented prompt.
  - **Use Cases:** Contextual chatbots, personalized search, real-time data summarization, and improved content generation.

- **Amazon Titan Embedding:** A lightweight model designed for high-accuracy retrieval tasks. It translates text into numerical embeddings and supports over 100 languages, making it ideal for multilingual applications.

#### Pretrained AI Services on AWS

AWS offers a suite of ready-to-use AI services to address common business needs:
- **Amazon Rekognition:** Image and video analysis.
- **Amazon Translate:** Text detection and translation.
- **Amazon Textract:** Text and layout extraction from documents.
- **Amazon Transcribe:** Speech-to-text conversion.
- **Amazon Polly:** Text-to-speech synthesis.
- **Amazon Comprehend:** Text analysis for insights and relationships.
- **Amazon Kendra:** Intelligent search capabilities.
- **Amazon Lookout:** Anomaly detection in metrics, equipment, and images.
- **Amazon Personalize:** Personalized recommendations for users.

#### Amazon Bedrock AgentCore

The session introduced **Amazon Bedrock AgentCore**, a platform for securely deploying and scaling AI agents in production. Key features include:
- **Memory:** Enables agents to remember past interactions and learn over time.
- **Identity and Access Controls:** Ensures secure execution of agent workflows.
- **Tool Integration:** Supports tools like browsers and code interpreters for complex workflows.
- **Observability:** Provides insights into agent interactions for auditing and debugging.
- **Frameworks for Building Agents:** Includes CrewAI, LangChain, OpenAI Agents SDK, and more.

#### Live Demo: AMZPhoto
The demo showcased a face recognition application built using AWS AI services. The application demonstrated the seamless integration of Amazon Rekognition for image analysis.

### Key Takeaways

- **Amazon Bedrock as a GenAI Hub:** Bedrock simplifies access to foundation models from top providers, enabling rapid development of AI solutions.
- **Prompt Engineering and RAG:** Effective prompting techniques and retrieval-augmented generation can significantly enhance model performance.
- **Titan Embeddings for Search:** Amazon Titan Embedding is a powerful tool for high-accuracy information retrieval.
- **Pretrained AI Services:** AWS offers a wide range of services to address diverse AI/ML needs, from image analysis to personalized recommendations.
- **AgentCore for Production-Ready AI:** Bedrock AgentCore addresses the challenges of deploying AI agents at scale, ensuring security, scalability, and observability.

### Applying Insights to Work

The knowledge gained from this event can be applied in several ways:
- **Integrating Foundation Models:** Incorporating foundation models into future projects to enhance AI capabilities.
- **Optimizing Workflows with RAG:** Using retrieval-augmented generation to improve the quality of AI-driven solutions.
- **Leveraging Pretrained Services:** Utilizing AWS AI services like Rekognition and Textract to automate repetitive tasks and improve efficiency.
- **Building Scalable AI Agents:** Exploring Bedrock AgentCore for deploying secure and scalable AI agents in production environments.

### Event Experience

The event was highly engaging and informative, with well-prepared speakers and interactive sessions. Key highlights of the experience included:
- **Q&A Session:** A team member raised a critical question about handling high volumes of alerts in an architecture using SNS for GuardDuty findings. The solution provided was to integrate SQS to queue events, ensuring no alerts are missed.
- **Kahoot Quiz:** Was top 3 until the Ragnarok began...
- **Networking:** Formed an unofficial group, "Mèo Cam Đeo Khăn," in collaboration with other attendees, fostering connections and future collaboration opportunities.

### Event Photos
- ![Mèo Cam Đeo Khăn group](../4.2-Event2/Meocamdeokhan.jpg)