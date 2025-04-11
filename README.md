## ⚠️ Deployment Note

Due to resource limitations during deployment, we were unable to run the full Ollama local LLM pipeline, which requires at least 16GB RAM. Our available virtual machines could not support this without switching to a paid cloud instance (e.g., AWS EC2). As a result, we have included a placeholder link or mocked output in the submission to demonstrate the expected agent interactions and flow.

The system has been structured modularly such that the actual LLM agents can be integrated seamlessly once appropriate compute resources become available.


# CVAgent: AI-Driven Resume Screening & Job Matching Platform

CVAgent is a streamlined AI-powered recruitment platform that automates the end-to-end process of candidate screening, resume analysis, job description matching, and personalized email generation — all using a modular, multi-agent architecture powered by local LLMs like Mistral through Ollama. Built using Python and Streamlit, this system helps recruiters and candidates connect efficiently through intelligent automation.

## 🚀 Features

- Resume parsing from uploaded PDFs  
- Job description summarization and standardization  
- Intelligent candidate-job matching using LLMs  
- Personalized acceptance/rejection email generation  
- User/Admin role-based dashboard and functionality  
- Secure application logging and job tracking  
- Local LLM integration using Ollama and Mistral  
- Relational database with SQLite for applications, jobs, and users  

## 🧠 Agent Architecture

| Agent           | Task                                | Input                    | Output                                |
|------------------|-------------------------------------|---------------------------|----------------------------------------|
| AnalyzerAgent    | Extract structured CV data          | Raw resume PDF            | JSON: Name, Education, Skills, Experience |
| SummarizerAgent  | Simplify job descriptions           | Raw JD text               | JSON: Role, Responsibilities, Skills   |
| MatcherAgent     | Score candidate-job fit             | CV JSON + JD JSON         | JSON: Score, Recommendation, Reason    |
| GeneratorAgent   | Generate notification emails        | Matching Output           | Subject + Body (Email Text)            |

Each agent is stateless and uses standard JSON for input/output communication, allowing flexibility and easy debugging.

## 🛠️ Technologies Used

- Python  
- Streamlit  
- SQLite3  
- Ollama (for local LLM deployment)  
- Mistral (as language model backend)  
- LangChain (for prompt orchestration)  
- PDFplumber (PDF parsing)  
- SMTP for email dispatch  


## ⚙️ Database Schema

- User (userid, username, email, password_hash, role)  
- Job (jobid, company_name, role, description, skills, openings, salary, created_by)  
- Application (applicationid, userid, jobid, applied_at, status)  

## ✅ How it Works

1. A candidate uploads their resume on the User Dashboard.  
2. Agents process the resume and evaluate fit against selected jobs.  
3. The system stores the application, generates a match score and email.  
4. Final selection/rejection email is sent automatically.  
5. Admins can monitor and accept/reject applications.  






