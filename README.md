# System Functional Evaluation Agent

A sophisticated loan management system evaluation platform that enables non-technical users to test business workflows, validate API endpoints, and assess system functionality through intelligent natural language interactions.

## 📋 Overview

The System Functional Evaluation Agent is a comprehensive solution designed to streamline the evaluation and validation of loan management systems. It combines a powerful backend architecture with an intuitive, user-friendly frontend to enable business stakeholders to quickly assess system capabilities, test workflows, and validate API responses without requiring technical expertise.

### Business Value

This system addresses a critical gap in financial services evaluation: **the ability for non-technical business users to independently validate system functionality**. Whether you're a loan officer testing underwriting workflows, a compliance officer validating business rules, or a operations manager evaluating system integration, this platform empowers you to:

- ✅ Test complete loan management workflows without writing code
- ✅ Validate API responses and system behavior in real-time
- ✅ Generate realistic test scenarios automatically
- ✅ Make data-driven decisions about system suitability
- ✅ Document system capabilities and limitations

## 🎯 Key Capabilities

### Intelligent Workflow Evaluation
- **Natural Language Interface**: Simply describe what you want to test, and the system understands your intent
- **Automatic API Selection**: Intelligently identifies relevant API endpoints based on your requirements
- **Smart Test Data Generation**: Creates realistic test scenarios that match your business context

### Comprehensive Response Analysis
- **Executive Summary**: High-level overview of test results in business terms
- **Pass/Fail Decision**: Clear determination of system behavior against expectations
- **Detailed Reasoning**: Full LLM analysis explaining the results
- **Test Documentation**: Complete record of inputs used and system responses received

### Flexible Result Visualization
- **Table View**: Structured data in familiar spreadsheet format
- **List View**: Detailed, readable presentation of results
- **Visual Mode**: Charts and diagrams for quick understanding

### System Health Monitoring
- **Service Status**: Real-time health checks for API and Agent servers
- **Performance Metrics**: Monitor system responsiveness and availability
- **Configuration Management**: Easy setup of API endpoints and Swagger specifications

## 🏗️ Architecture

The System Functional Evaluation Agent is built on a modern, scalable three-tier architecture:

```
┌─────────────────────────────────────────────────────┐
│                    Frontend Layer                    │
│          (React + Tailwind CSS Application)          │
│  - User-Friendly Interface                          │
│  - Real-Time Response Display                       │
│  - Configuration & Health Monitoring                 │
└──────────────────┬──────────────────────────────────┘
                   │
        ┌──────────┴──────────┐
        ▼                     ▼
┌─────────────────┐  ┌────────────────────┐
│   Agent Server  │  │   API Server       │
│                 │  │                    │
│ - OpenAPI Read  │  │ - Loan Management  │
│ - Endpoint      │  │ - Underwriting     │
│   Selection     │  │ - Workflow Valid.  │
│ - Test Gen      │  │ - Applications     │
│ - Response      │  │ - Users & Groups   │
│   Evaluation    │  │ - Payments         │
└─────────────────┘  └────────────────────┘
```

## 📁 Folder Structure

```
System-Functional-Evaluation-Agent/
├── api-server/                    # REST API for loan management
│   ├── src/
│   │   ├── controllers/
│   │   ├── models/
│   │   ├── routes/
│   │   └── services/
│   ├── config/
│   └── package.json
│
├── agent-server/                  # Intelligent evaluation engine
│   ├── src/
│   │   ├── swagger-parser/
│   │   ├── endpoint-selector/
│   │   ├── test-data-generator/
│   │   ├── api-invoker/
│   │   └── response-evaluator/
│   ├── config/
│   └── package.json
│
├── frontend/                      # React user interface
│   ├── src/
│   │   ├── components/
│   │   │   ├── ChatInterface/
│   │   │   ├── ResultsDisplay/
│   │   │   ├── HealthMonitor/
│   │   │   └── Configuration/
│   │   ├── pages/
│   │   ├── services/
│   │   ├── styles/
│   │   └── App.tsx
│   ├── public/
│   └── package.json
│
├── docs/                         # Documentation
│   ├── API_SPECIFICATION.md
│   ├── DEPLOYMENT.md
│   └── USER_GUIDE.md
│
└── README.md                     # This file
```

## 🛠️ Tech Stack

### API Server
- **Runtime**: Node.js / Express.js
- **Language**: TypeScript/JavaScript
- **Database**: PostgreSQL (or your chosen database)
- **Validation**: Joi/Yup
- **Documentation**: Swagger/OpenAPI 3.0

### Agent Server
- **Runtime**: Node.js / Python
- **Language**: TypeScript/JavaScript or Python
- **AI Framework**: LLM integration (OpenAI/Claude/Local models)
- **Libraries**: Swagger-parser, Axios
- **Processing**: Async job queue support

### Frontend
- **Framework**: React 18+
- **Styling**: Tailwind CSS
- **UI Components**: Headless UI / Shadcn
- **State Management**: React Context / Redux
- **HTTP Client**: Axios
- **Build Tool**: Vite / Create React App

## 📦 Setup Instructions

### Prerequisites
- Node.js 16+ (for JavaScript/TypeScript) or Python 3.8+ (for Python services)
- npm or yarn package manager
- Git
- Modern web browser (Chrome, Firefox, Safari, Edge)

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/yourusername/System-Functional-Evaluation-Agent.git
cd System-Functional-Evaluation-Agent
```

2. **Install dependencies for all services**
```bash
# API Server
cd api-server
npm install
cd ..

# Agent Server
cd agent-server
npm install
cd ..

# Frontend
cd frontend
npm install
cd ..
```

3. **Environment Configuration**

Create `.env` files in each directory:

**api-server/.env**
```
PORT=3000
DATABASE_URL=postgresql://user:password@localhost:5432/loan_management
NODE_ENV=development
```

**agent-server/.env**
```
PORT=3001
API_SERVER_URL=http://localhost:3000
OPENAI_API_KEY=your_api_key_here
LOG_LEVEL=info
```

**frontend/.env**
```
REACT_APP_API_SERVER_URL=http://localhost:3001
REACT_APP_AGENT_SERVER_URL=http://localhost:3001
```

## 🚀 How to Run

### 1. Start the API Server
```bash
cd api-server
npm run dev
```
The API Server will be available at `http://localhost:3000`

### 2. Start the Agent Server
```bash
cd agent-server
npm run dev
```
The Agent Server will be available at `http://localhost:3001`

### 3. Start the Frontend
```bash
cd frontend
npm run dev
```
The Frontend will be available at `http://localhost:5173` (or your configured port)

### Verify System Health
Once all services are running, visit the frontend and navigate to the **Health & Status** view to confirm all services are connected and operational.

## 💡 Example Usage

### Scenario: Validate Loan Application Workflow

1. **Open the Frontend**
   - Navigate to the chat interface
   - Configure your API base URL (if not pre-configured)

2. **Enter Your Request**
   ```
   "Test the loan application process for a $250,000 mortgage with a 20-year term. 
   Validate that the system correctly calculates monthly payments and generates 
   an accurate amortization schedule."
   ```

3. **System Processing**
   - Agent Server reads the API specification
   - Identifies relevant endpoints: `/applications/create`, `/underwriting/calculate-payment`, `/loans/generate-schedule`
   - Generates realistic test data matching your criteria
   - Invokes each endpoint sequentially
   - Evaluates responses against business logic

4. **Review Results**
   - **Summary View**: "Loan application workflow completed successfully. Monthly payment: $1,432.47. Amortization schedule generated."
   - **Decision**: ✅ PASS - System behaves correctly
   - **Table View**: Detailed breakdown of each API call and response
   - **Reasoning**: LLM explanation of decision logic

### Scenario: Check System Status
Simply navigate to the **Health & Status**

