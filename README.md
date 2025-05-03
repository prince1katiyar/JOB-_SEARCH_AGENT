# Job Search Assistant

**Purpose:**  
Job Search Assistant is a comprehensive solution designed to help users search for jobs and match their resumes to ideal opportunities using AI and real-time data scraping. The system uses advanced technologies such as NLP, AI-powered recommendation engines, vector-based search, and cloud-native services for real-time job listing scraping and recommendation processing.

## Project Overview
This project consists of multiple services and components that work together to deliver personalized job recommendations and resume matching. It integrates real-time scraping, AI-powered NLP services, and cloud-native architecture to ensure scalability, security, and high availability.

## Technologies Used
- AWS EventBridge
- Docker
- Playwright (for web scraping)
- PostgreSQL (RDS/Aurora)
- OpenAI GPT-4 and GPT-3.5 Turbo
- Pinecone or Chroma (Vector Databases)
- FastAPI (API Backend)
- React/Next.js (Frontend)
- AWS Lambda, SQS, CloudWatch, Terraform
- CI/CD with GitHub Actions

## Components

### 1. Real-Time Scraper Service
**Purpose:** Periodically collect job data from multiple websites in real-time with robust automation.  
- **Trigger:** AWS EventBridge Scheduler (cron job, hourly)
- **Scraping Tools:** Dockerized Playwright (for JS-rendered content), Firecrawl (AI-assisted dynamic crawler)
- **Output Format:** Structured JSON or CSV

### 2. Data Storage (PostgreSQL)
**Purpose:** Central storage for structured data from scraper and AI services.  
- **Database Design:** Tables for jobs, resumes, companies; JSONB columns for dynamic fields
- **High Availability:** Amazon RDS/Aurora PostgreSQL, Multi-AZ deployment, automated backups

### 3. NLP Services (OpenAI GPT)
**Purpose:** Enhance data with AI—summarize jobs, parse resumes, extract skills/experience.  
- **Models Used:** GPT-4o for high-quality results, GPT-3.5 Turbo for cost-efficient processing
- **Tasks:** Job Summarization, Resume Parsing, Skill/Experience Extraction

### 4. Vector Store (Pinecone or Chroma)
**Purpose:** Semantic search and embedding-based similarity matching between resumes and jobs.  
- **Functionality:** Store embeddings, k-NN search, metadata tagging

### 5. Recommendation Engine
**Purpose:** Provide personalized job recommendations to users.  
- **Steps:** Convert resumes to vector embeddings, Match against job vectors, Apply SQL filters, Use GPT for re-ranking results

### 6. API Backend (FastAPI)
**Purpose:** Handle all frontend communication, user interactions, and service orchestration.  
- **Endpoints:** /jobs, /resumes, /recommendations, /redirect
- **Security:** JWT-based auth via Amazon Cognito

### 7. Frontend (React/Next.js)
**Purpose:** Modern UI for users to upload resumes, browse jobs, and receive recommendations.  
- **Features:** Resume upload, recommendation view, search, filters, user login

### 8. Redirect/Click Tracking
**Purpose:** Log user interactions (job apply clicks) for analytics and recommendation feedback.  
- **Mechanism:** /redirect route logs events and redirects

### 9. CI/CD Pipelines
**Purpose:** Automate application deployment and infrastructure updates.  
- **Tools:** GitHub Actions or AWS CodePipeline

### 10. Monitoring & Security
**Purpose:** Ensure high observability, secure access, and proactive alerting.  
- **Observability:** CloudWatch Logs, CloudWatch Metrics
- **Security:** VPC, IAM roles, Secrets Manager

## Installation
To get started with the Job Search Assistant project, follow these steps:

1. Clone this repository:
    ```bash
    git clone https://github.com/yourusername/Job-Search-Assistant.git
    ```

2. Navigate to the project directory:
    ```bash
    cd Job-Search-Assistant
    ```

3. Install required dependencies:
    ```bash
    pip install -r requirements.txt
    ```

4. Set up the necessary environment variables (e.g., AWS credentials, database URLs).

5. Run the project locally or deploy to AWS (instructions to be provided).

## Contributing
Feel free to contribute by creating issues or submitting pull requests.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
