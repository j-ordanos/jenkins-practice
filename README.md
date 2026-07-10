# Jenkins Practice

A simple Node.js project used for demonstrating and practicing Continuous Integration using **Jenkins Declarative Pipelines** and **GitHub Webhooks**.

This repository serves as a practical, foundational playground to explore how Jenkins orchestrates build, test, and execution tasks, while triggering automatically on code changes.

## 🚀 Features

- **Declarative Pipeline**: Uses a `Jenkinsfile` for infrastructure-as-code CI definition.
- **Automated Triggers**: Designed to work seamlessly with GitHub webhooks.
- **Node.js Environment**: A minimal application (`app.js`) and test scaffold in `package.json` to simulate real-world app building.

## 🏗️ Pipeline Architecture

The `Jenkinsfile` defines the following sequential stages:

1. **Checkout**: Jenkins automatically pulls the latest source code from the branch.
2. **Install Dependencies**: Runs `npm install` to set up the environment.
3. **Run Tests**: Executes `npm test` to validate the code.
4. **Run Application**: Runs `npm start` (executes `app.js`).

### Post Actions
The pipeline gives direct feedback upon completion:
- **always**: Logs "Pipeline execution completed."
- **success**: Logs "Build completed successfully!"
- **failure**: Logs "Build failed!"

## ⚙️ Prerequisites

To run this locally or on a server, you will need:
- [Node.js](https://nodejs.org/)
- npm (comes with Node.js)
- A running [Jenkins](https://www.jenkins.io/) server.

## 💻 Local Development

Test the pipeline steps manually on your local machine:

```bash
# Install dependencies
npm install

# Run the tests
npm test

# Start the application
npm start
```

## 🔗 Setting up the Webhook

To connect this repository to Jenkins for automated builds:
1. Go to your GitHub repository -> **Settings** -> **Webhooks**.
2. Add a webhook with Payload URL: `http://<your-jenkins-ip>:<port>/github-webhook/`
3. Set Content type to `application/json`.
4. Choose to trigger on `Just the push event`.
5. In your Jenkins Pipeline configuration, check the **GitHub hook trigger for GITScm polling** box.
