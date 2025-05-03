<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Job Search Assistant</title>
</head>
<body>
    <h1>Job Search Assistant</h1>
    <p><strong>Purpose:</strong> Job Search Assistant is a comprehensive solution designed to help users search for jobs and match their resumes to ideal opportunities using AI and real-time data scraping. The system uses advanced technologies such as NLP, AI-powered recommendation engines, vector-based search, and cloud-native services for real-time job listing scraping and recommendation processing.</p>

    <h2>Project Overview</h2>
    <p>This project consists of multiple services and components that work together to deliver personalized job recommendations and resume matching. It integrates real-time scraping, AI-powered NLP services, and cloud-native architecture to ensure scalability, security, and high availability.</p>

    <h3>Technologies Used</h3>
    <ul>
        <li>AWS EventBridge</li>
        <li>Docker</li>
        <li>Playwright (for web scraping)</li>
        <li>PostgreSQL (RDS/Aurora)</li>
        <li>OpenAI GPT-4 and GPT-3.5 Turbo</li>
        <li>Pinecone or Chroma (Vector Databases)</li>
        <li>FastAPI (API Backend)</li>
        <li>React/Next.js (Frontend)</li>
        <li>AWS Lambda, SQS, CloudWatch, Terraform</li>
        <li>CI/CD with GitHub Actions</li>
    </ul>

    <h2>Components</h2>

    <h3>1. Real-Time Scraper Service</h3>
    <p><strong>Purpose:</strong> Periodically collect job data from multiple websites in real-time with robust automation.</p>
    <ul>
        <li><strong>Trigger:</strong> AWS EventBridge Scheduler (cron job, hourly)</li>
        <li><strong>Scraping Tools:</strong> Dockerized Playwright (for JS-rendered content), Firecrawl (AI-assisted dynamic crawler)</li>
        <li><strong>Output Format:</strong> Structured JSON or CSV</li>
    </ul>

    <h3>2. Data Storage (PostgreSQL)</h3>
    <p><strong>Purpose:</strong> Central storage for structured data from scraper and AI services.</p>
    <ul>
        <li><strong>Database Design:</strong> Tables for jobs, resumes, companies; JSONB columns for dynamic fields</li>
        <li><strong>High Availability:</strong> Amazon RDS/Aurora PostgreSQL, Multi-AZ deployment, automated backups</li>
    </ul>

    <h3>3. NLP Services (OpenAI GPT)</h3>
    <p><strong>Purpose:</strong> Enhance data with AI—summarize jobs, parse resumes, extract skills/experience.</p>
    <ul>
        <li><strong>Models Used:</strong> GPT-4o for high-quality results, GPT-3.5 Turbo for cost-efficient processing</li>
        <li><strong>Tasks:</strong> Job Summarization, Resume Parsing, Skill/Experience Extraction</li>
    </ul>

    <h3>4. Vector Store (Pinecone or Chroma)</h3>
    <p><strong>Purpose:</strong> Semantic search and embedding-based similarity matching between resumes and jobs.</p>
    <ul>
        <li><strong>Functionality:</strong> Store embeddings, k-NN search, metadata tagging</li>
    </ul>

    <h3>5. Recommendation Engine</h3>
    <p><strong>Purpose:</strong> Provide personalized job recommendations to users.</p>
    <ul>
        <li><strong>Steps:</strong> Convert resumes to vector embeddings, Match against job vectors, Apply SQL filters, Use GPT for re-ranking results</li>
    </ul>

    <h3>6. API Backend (FastAPI)</h3>
    <p><strong>Purpose:</strong> Handle all frontend communication, user interactions, and service orchestration.</p>
    <ul>
        <li><strong>Endpoints:</strong> /jobs, /resumes, /recommendations, /redirect</li>
        <li><strong>Security:</strong> JWT-based auth via Amazon Cognito</li>
    </ul>

    <h3>7. Frontend (React/Next.js)</h3>
    <p><strong>Purpose:</strong> Modern UI for users to upload resumes, browse jobs, and receive recommendations.</p>
    <ul>
        <li><strong>Features:</strong> Resume upload, recommendation view, search, filters, user login</li>
    </ul>

    <h3>8. Redirect/Click Tracking</h3>
    <p><strong>Purpose:</strong> Log user interactions (job apply clicks) for analytics and recommendation feedback.</p>
    <ul>
        <li><strong>Mechanism:</strong> /redirect route logs events and redirects</li>
    </ul>

    <h3>9. CI/CD Pipelines</h3>
    <p><strong>Purpose:</strong> Automate application deployment and infrastructure updates.</p>
    <ul>
        <li><strong>Tools:</strong> GitHub Actions or AWS CodePipeline</li>
    </ul>

    <h3>10. Monitoring & Security</h3>
    <p><strong>Purpose:</strong> Ensure high observability, secure access, and proactive alerting.</p>
    <ul>
        <li><strong>Observability:</strong> CloudWatch Logs, CloudWatch Metrics</li>
        <li><strong>Security:</strong> VPC, IAM roles, Secrets Manager</li>
    </ul>

    <h2>Installation</h2>
    <p>To get started with the Job Search Assistant project, follow these steps:</p>
    <ol>
        <li>Clone this repository:</li>
        <pre>git clone https://github.com/yourusername/Job-Search-Assistant.git</pre>
        <li>Navigate to the project directory:</li>
        <pre>cd Job-Search-Assistant</pre>
        <li>Install required dependencies:</li>
        <pre>pip install -r requirements.txt</pre>
        <li>Set up the necessary environment variables (e.g., AWS credentials, database URLs).</li>
        <li>Run the project locally or deploy to AWS (instructions to be provided).</li>
    </ol>

    <h2>Contributing</h2>
    <p>Feel free to contribute by creating issues or submitting pull requests.</p>

    <h2>License</h2>
    <p>This project is licensed under the MIT License - see the <a href="LICENSE">LICENSE</a> file for details.</p>
</body>
</html>
