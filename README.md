# Jenkins Practice

Simple Node.js project using a Jenkins Declarative Pipeline.

## Pipeline Stages

- **Checkout** – source already checked out by Jenkins  
- **Install Dependencies** – `npm install`  
- **Run Tests** – `npm test`  
- **Run Application** – `npm start`  

## Post Actions

- **always:** Pipeline execution completed  
- **success:** Build completed successfully  
- **failure:** Build failed  

## Prerequisites

- Node.js
- npm
- Jenkins

## Local Run

```bash
npm install
npm test
npm start
```
