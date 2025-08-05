# My Node.js CI/CD Demo App 🚀

This project demonstrates a simple CI/CD pipeline using **Jenkins** and **Docker** to build, test, and deploy a basic Node.js application. It’s built for local experimentation and DevOps learning.

---

## 🧰 Technologies Used

- Node.js
- Mocha (for testing)
- Docker
- Jenkins
- GitHub

---

## 📁 Project Structure


---

## 🧪 Jenkins Pipeline Stages

This project uses a **declarative Jenkins pipeline**, triggered from GitHub commits.

1. **Checkout Code**  
   Pulls code from `main` branch of GitHub repository.

2. **Install Dependencies**  
   Runs `npm install` via Jenkins using configured NodeJS tool.

3. **Run Tests**  
   Executes Mocha unit tests (`test.js`).

4. **Build Docker Image**  
   Builds an image: `paraajwalweebe/node-app`.

5. **Push Docker Image**  
   Pushes to DockerHub using Jenkins stored credentials.

---

## ⚙️ Prerequisites to Run Locally

- Jenkins installed via Homebrew or native `.pkg`
- Node.js & npm installed
- Docker Desktop running
- GitHub repository with a `Jenkinsfile`
- DockerHub account & credentials added to Jenkins:
  - ID: `dockerhub-creds`
  - Username + password/token

---

## 🐳 Build Locally (Optional)

```bash
# Install dependencies
npm install

# Run tests
npm test

# Build and run Docker container
docker build -t my-node-app .
docker run -p 8080:8080 my-node-app

**CI/CD Workflow**
Push a commit to main on GitHub

Jenkins auto-fetches code and executes the pipeline

If tests pass, Docker image is built and pushed to DockerHub
