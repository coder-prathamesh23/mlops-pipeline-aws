# AWS MLOps Pipeline with GitHub Actions 🚀

This project demonstrates an end-to-end machine learning pipeline on AWS, automated using **GitHub Actions**. It preprocesses data, trains a model on SageMaker, deploys it via an endpoint, and serves predictions using a REST API (API Gateway + Lambda).

## 📌 Features

- ✅ Data preprocessing using AWS Lambda
- ✅ Model training with Amazon SageMaker (Linear Learner)
- ✅ Model deployment via Step Functions
- ✅ REST API for inference via API Gateway
- ✅ CI/CD pipeline triggered by GitHub Actions

## 🛠️ Tech Stack

- **AWS Services**: SageMaker, Lambda, Step Functions, API Gateway, S3, IAM
- **Automation**: GitHub Actions
- **Language**: Python
- **Containerized**: Preprocessing code via Docker (Lambda)

## 🔁 Workflow

```mermaid
graph TD
    A[Push to GitHub] --> B[GitHub Actions Trigger]
    B --> C[Trigger Step Function]
    C --> D[Lambda Preprocessing]
    D --> E[SageMaker Training Job]
    E --> F[Create Model]
    F --> G[Deploy Endpoint]
    G --> H[API Gateway + Lambda Inference]


.
├── .github/
│   └── workflows/
│       └── mlops-pipeline.yml       # GitHub Actions CI/CD
├── lambda-preprocess-container/     # Dockerized Lambda for preprocessing
├── step-functions/                  # Step Function definition JSON
├── README.md
└── ....

