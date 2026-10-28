# Invenza
### An AI-Driven Multimodal Product Catalog System and Inventory Optimization

Invenza is an AI-driven platform designed to bring product catalog management and inventory optimization together. It supports product information management and AI-assisted business insights to help merchants make informed decisions.

## Project Overview

The project combines a web application, a backend API, and an AI service to support its product catalog and inventory-related workflows.

## Technology Stack

- **Frontend:** React and Vite
- **Backend:** Node.js and Express
- **AI Service:** Python and FastAPI
- **Database:** MongoDB
- **AI and data processing:** Machine learning and AI integrations used by the project

## Project Structure

- `client/` — Frontend application
- `server/` — Backend API and application services
- `ai-service/` — AI service and related processing components

## Running Locally

Start each component in a separate terminal.

### 1. Backend

```powershell
Set-Location ".\server"
npm install
npm run dev
```

### 2. AI Service

```powershell
Set-Location ".\ai-service"
python -m pip install -r requirements.txt
python -m uvicorn main:app --host 127.0.0.1 --port 8000
```

### 3. Frontend

```powershell
Set-Location ".\client"
npm install
npm run dev
```

Open the local frontend URL printed by Vite in the terminal.

Configure environment variables using the provided `.env.example` files. Never commit actual API keys, passwords, database credentials, or other secrets.

## Project Purpose

Invenza explores how multimodal product information and AI-assisted analysis can be integrated into a product catalog and inventory optimization system.

## License and Attribution

Retain all applicable third-party licenses, notices, and required attributions for included dependencies and reused components.
