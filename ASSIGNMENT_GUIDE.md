# Complete Assignment Guide - Step by Step

This document provides detailed step-by-step instructions for completing the DevOps assignment.

## Question 1: Git Version Control (10 Marks)

### Part 1a: Setup Local Git Repository (2 Marks)

**Step 1: Navigate to Project Directory**
```bash
cd /Users/nareshkumarthodupunoori/Desktop/BITS_SGA
```

**Step 2: Initialize Git Repository**
```bash
git init
```
**Expected Output:**
```
Initialized empty Git repository in /Users/nareshkumarthodupunoori/Desktop/BITS_SGA/.git/
```

**Step 3: Check Status**
```bash
git status
```
**Expected Output:** Shows untracked files (index.html, about.html, contact.html, Dockerfile, etc.)

**Screenshot Required:** Terminal showing `git init` and `git status` commands

---

### Part 1b: Demonstrate Git Commands (6 Marks)

#### Command 1: git init
**Command:**
```bash
git init
```
**Explanation:** Initializes a new Git repository. Creates a `.git` directory that stores all version control information.

**Screenshot Required:** Terminal output showing repository initialization

---

#### Command 2: git status
**Command:**
```bash
git status
```
**Explanation:** Displays the state of the working directory and staging area. Shows which files are:
- Untracked (new files not yet added)
- Modified (changed files)
- Staged (ready to commit)

**Screenshot Required:** Terminal showing file status

---

#### Command 3: git add
**Command:**
```bash
git add .
# OR
git add index.html about.html contact.html Dockerfile
```
**Explanation:** Stages files for commit. The `.` adds all files in the current directory.

**After running `git add`, run `git status` again to see files are now staged (green).**

**Screenshot Required:** 
1. Terminal showing `git add .` command
2. Terminal showing `git status` after add (showing staged files)

---

#### Command 4: git commit
**Command:**
```bash
git commit -m "Initial commit: Add web application files"
```
**Explanation:** Creates a snapshot of the staged changes with a descriptive message. Each commit has a unique hash.

**Screenshot Required:** Terminal showing commit message and commit hash

---

#### Command 5: git log
**Command:**
```bash
git log
# OR for compact view
git log --oneline
# OR for visual graph
git log --graph --oneline --all
```
**Explanation:** Shows the commit history with author, date, and commit messages.

**Screenshot Required:** Terminal showing commit history

---

#### Command 6: git branch
**Command:**
```bash
# List all branches
git branch

# Create a new branch
git branch feature-branch

# List branches again to see the new branch
git branch
```
**Explanation:** 
- Lists all branches (current branch marked with *)
- Creates a new branch without switching to it

**Screenshot Required:** Terminal showing branch creation and listing

---

#### Command 7: git switch
**Command:**
```bash
# Switch to the new branch
git switch feature-branch

# Verify you're on the new branch
git branch

# Switch back to main
git switch main
```
**Explanation:** Changes the working directory to the specified branch. All files update to match that branch's state.

**Screenshot Required:** Terminal showing branch switching

---

### Part 1c: GitHub Integration (2 Marks)

**Step 1: Create GitHub Account**
- Go to https://github.com
- Sign up for a new account (if you don't have one)

**Step 2: Create New Repository**
1. Click the "+" icon in top right → "New repository"
2. Repository name: `devops-assignment` (or your choice)
3. Description: "DevOps Assignment - Git and Docker"
4. Choose Public or Private
5. **DO NOT** initialize with README, .gitignore, or license
6. Click "Create repository"

**Step 3: Connect Local Repository to GitHub**
```bash
# Add remote repository (replace username and repo-name)
git remote add origin https://github.com/your-username/your-repo-name.git

# Verify remote was added
git remote -v
```

**Step 4: Push to GitHub**
```bash
# Push main branch to GitHub
git push -u origin main
```

**Screenshots Required:**
1. GitHub repository creation page
2. Terminal showing `git remote add` command
3. Terminal showing `git push` command and successful push
4. GitHub repository page showing all files

**Deliverable:** Link to GitHub repository

---

## Question 2: Docker Containerization (10 Marks)

### Part 2a: Custom Docker Image (2 Marks)

**Dockerfile Content:**
```dockerfile
FROM nginx:alpine
COPY index.html /usr/share/nginx/html/
COPY about.html /usr/share/nginx/html/
COPY contact.html /usr/share/nginx/html/
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
```

**Explanation:**
- `FROM nginx:alpine`: Uses lightweight nginx web server as base image
- `COPY`: Copies HTML files to nginx's web directory
- `EXPOSE 80`: Documents that the container listens on port 80
- `CMD`: Starts nginx in foreground mode

**Screenshot Required:** Dockerfile content (can be text or screenshot)

---

### Part 2b: Docker Image Creation Steps (2 Marks)

**Step 1: Build Docker Image**
```bash
# Navigate to project directory
cd /Users/nareshkumarthodupunoori/Desktop/BITS_SGA

# Build the image
docker build -t devops-assignment:latest .
```

**Step 2: Verify Image Creation**
```bash
# List all images
docker images

# You should see devops-assignment:latest in the list
```

**Screenshots Required:**
1. Terminal showing `docker build` command
2. Terminal showing build process output (layers being built)
3. Terminal showing `docker images` with the new image listed

---

### Part 2c: Push to Docker Hub (3 Marks)

**Step 1: Create Docker Hub Account**
- Go to https://hub.docker.com
- Sign up for a new account (if you don't have one)
- Note your username

**Step 2: Login to Docker Hub**
```bash
docker login
```
Enter your Docker Hub username and password when prompted.

**Step 3: Tag Image for Docker Hub**
```bash
# Replace 'your-username' with your Docker Hub username
docker tag devops-assignment:latest your-username/devops-assignment:latest
```

**Step 4: Push Image to Docker Hub**
```bash
docker push your-username/devops-assignment:latest
```

**Screenshots Required:**
1. Terminal showing `docker login` (username visible, password hidden)
2. Terminal showing `docker tag` command
3. Terminal showing `docker push` command and upload progress
4. Docker Hub repository page showing the pushed image

**Deliverable:** Link to Docker Hub repository

---

### Part 2d: Container Deployment Demonstration (3 Marks)

**Step 1: Run Container Locally**
```bash
# Run container in detached mode, mapping port 8080 (host) to 80 (container)
docker run -d -p 8080:80 --name devops-web your-username/devops-assignment:latest
```

**Explanation:**
- `-d`: Runs container in detached mode (background)
- `-p 8080:80`: Maps host port 8080 to container port 80
- `--name devops-web`: Names the container
- Last argument: Image name

**Step 2: Verify Container is Running**
```bash
# List running containers
docker ps

# View container logs
docker logs devops-web
```

**Step 3: Access Web Application**
- Open web browser
- Navigate to: `http://localhost:8080`
- You should see the home page
- Navigate to About and Contact pages

**Step 4: Stop and Remove Container (Cleanup)**
```bash
# Stop the container
docker stop devops-web

# Remove the container
docker rm devops-web
```

**Screenshots Required:**
1. Terminal showing `docker run` command
2. Terminal showing `docker ps` with running container
3. Terminal showing `docker logs devops-web`
4. Browser screenshot showing home page (http://localhost:8080)
5. Browser screenshot showing About page
6. Browser screenshot showing Contact page

---

## Complete Command Sequence

Here's the complete sequence of commands in order:

### Git Setup
```bash
cd /Users/nareshkumarthodupunoori/Desktop/BITS_SGA
git init
git status
git add .
git commit -m "Initial commit: Add web application files"
git log --oneline
git branch feature-branch
git switch feature-branch
git switch main
git remote add origin https://github.com/your-username/your-repo.git
git push -u origin main
```

### Docker Setup
```bash
docker build -t devops-assignment:latest .
docker images
docker login
docker tag devops-assignment:latest your-username/devops-assignment:latest
docker push your-username/devops-assignment:latest
docker run -d -p 8080:80 --name devops-web your-username/devops-assignment:latest
docker ps
docker logs devops-web
# Open browser: http://localhost:8080
docker stop devops-web
docker rm devops-web
```

---

## Submission Document Template

Create a Word or PDF document with the following structure:

### Title Page
- Assignment Title: DevOps Assignment - Git & Docker
- Your Name
- Date

### Question 1: Git Version Control

#### 1a. Local Git Repository Setup
- Screenshot: `git init` command
- Screenshot: `git status` showing untracked files
- Explanation: "Initialized Git repository and checked status showing 3 HTML files and Dockerfile"

#### 1b. Git Commands Demonstration
- **git init:** Screenshot + explanation
- **git status:** Screenshot + explanation
- **git add:** Screenshot + explanation
- **git commit:** Screenshot + explanation
- **git log:** Screenshot + explanation
- **git branch:** Screenshot + explanation
- **git switch:** Screenshot + explanation

#### 1c. GitHub Integration
- Screenshot: GitHub repository creation
- Screenshot: `git remote add` command
- Screenshot: `git push` command
- Screenshot: GitHub repository page
- Link: https://github.com/your-username/your-repo

### Question 2: Docker Containerization

#### 2a. Custom Docker Image
- Screenshot/Text: Dockerfile content
- Explanation: "Dockerfile uses nginx:alpine base image and copies HTML files"

#### 2b. Docker Image Creation
- Screenshot: `docker build` command
- Screenshot: Build process output
- Screenshot: `docker images` showing created image
- Explanation: "Built Docker image successfully"

#### 2c. Push to Docker Hub
- Screenshot: `docker login`
- Screenshot: `docker tag` command
- Screenshot: `docker push` command
- Screenshot: Docker Hub repository page
- Link: https://hub.docker.com/r/your-username/devops-assignment

#### 2d. Container Deployment
- Screenshot: `docker run` command
- Screenshot: `docker ps` showing running container
- Screenshot: Browser - Home page
- Screenshot: Browser - About page
- Screenshot: Browser - Contact page
- Explanation: "Container running successfully on localhost:8080"

### Appendix
- Source Files: HTML pages, Dockerfile
- GitHub Repository Link
- Docker Hub Repository Link

---

## Troubleshooting

### Git Issues
- **Error: "not a git repository"** → Run `git init` first
- **Error: "nothing to commit"** → Run `git add .` first
- **Error: "remote origin already exists"** → Use `git remote set-url origin <url>` to update

### Docker Issues
- **Error: "Cannot connect to Docker daemon"** → Start Docker Desktop
- **Error: "permission denied"** → Use `sudo` (Linux) or ensure Docker Desktop is running (Mac/Windows)
- **Error: "port already in use"** → Change port: `-p 8081:80` instead of `-p 8080:80`
- **Error: "unauthorized"** → Run `docker login` first

---

## Grading Checklist

Ensure you have:
- ✅ 2-3 HTML web pages
- ✅ Git repository initialized
- ✅ Screenshots of all 7 Git commands
- ✅ GitHub repository created and pushed
- ✅ Dockerfile created
- ✅ Docker image built
- ✅ Image pushed to Docker Hub
- ✅ Container running locally
- ✅ Browser screenshots of web application
- ✅ All source files included
- ✅ Documentation with explanations

Good luck with your assignment!

