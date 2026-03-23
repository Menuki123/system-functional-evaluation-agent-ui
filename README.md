# System Functional Evaluation Agent

## Overview

The **System Functional Evaluation Agent** is a unified solution designed to simplify how API systems are tested, validated, and explained.

Instead of manually calling endpoints and interpreting responses, this system allows a user to simply provide a prompt describing what they want to test. The agent then automatically:

- Understands the request
- Identifies relevant API endpoints using Swagger/OpenAPI
- Generates appropriate test data
- Executes the APIs
- Evaluates results (pass/fail)
- Explains outcomes in both technical and non-technical language

This makes the system highly useful for both **technical teams** and **non-technical stakeholders**, enabling clear understanding of system behavior without deep technical knowledge.

---

## Key Capabilities

### Intelligent API Evaluation
- Automatically selects relevant endpoints based on user prompts
- Uses Swagger/OpenAPI definitions dynamically (no hardcoding)
- Supports different APIs through configuration

### Automated Test Execution
- Generates dummy payloads based on schema
- Invokes APIs automatically
- Handles multi-step workflows

### Smart Result Evaluation
- Determines pass / fail / review status
- Identifies validation issues and business rule failures
- Provides reasoning for each outcome

### User-Friendly Explanation
- Converts technical results into non-technical summaries
- Provides:
  - Summary
  - Decision (PASS / FAIL)
  - LLM reasoning
  - User-friendly explanation

### ChatGPT-Style Interaction
- Prompt-based testing interface
- Users can describe scenarios in natural language
- No need to understand API structure

### Multiple Visualization Modes
- Table view
- List view
- Visual breakdown
- Structured test results

### Environment Configuration (Portable Design)
- No hardcoded API dependencies
- Supports:
  - Custom API Base URL
  - Custom Swagger/OpenAPI input
  - Adjustable execution settings
- Can be reused for different API systems

### Workflow Validation Support
- Supports testing of:
  - Submission → Approval → Disbursement flows
  - Business rule validation
  - Data-driven decisions

---

## Architecture

This project consists of three main components:

### 1. API Server
Handles business logic and exposes REST APIs such as:
- Customer management
- Loan processing
- Underwriting validation
- Workflow management
- Payments and reporting

### 2. Agent Server
Acts as the intelligent evaluation engine:
- Reads Swagger/OpenAPI definitions
- Selects relevant endpoints
- Generates test inputs
- Executes API calls
- Evaluates responses
- Produces structured results

### 3. Frontend (React + Tailwind)
Provides a user-friendly interface:
- ChatGPT-style prompt input
- Configuration panel for environment setup
- Visualization of results
- Non-technical summaries for stakeholders

---

## Project Structure
loan-platform-suite/
├── api-server/
├── agent-server/
├── frontend/
├── README.md


---

## Tech Stack

- **Frontend:** React, Tailwind CSS, Vite
- **Backend:** Node.js, Express
- **Agent Logic:** LLM-style evaluation + Swagger-driven execution
- **API Definition:** OpenAPI / Swagger
- **Deployment:** GitHub, GitHub Pages (Frontend)

---

## How to Run the Project

### 1. API Server

```bash
cd api-server
npm install
node app.js

Runs on:

http://localhost:3000
2. Agent Server
cd agent-server
npm install
node server.js

Runs on:

http://localhost:4000
3. Frontend
cd frontend
npm install
npm run dev

Runs on:

http://localhost:5173
How It Works
User enters a prompt in the frontend
System configuration is applied (API base URL, Swagger source)
Agent:
Loads Swagger definition
Selects relevant endpoints
Generates test inputs
Executes API calls
Results are evaluated and returned
Frontend displays:
Summary
Decision
Reasoning
Test inputs
Execution results
