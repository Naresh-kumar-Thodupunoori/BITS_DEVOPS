# DevOps Assignment - Git & Docker

This project demonstrates essential DevOps practices including version control with Git and containerization with Docker.

## Project Structure

```
BITS_SGA/
├── index.html          # Home page
├── about.html          # About page
├── contact.html        # Contact page
├── Dockerfile          # Docker configuration
├── .dockerignore       # Files to exclude from Docker build
└── README.md           # This file
```

## Question 1: Git Version Control

### 1a. Setup Local Git Repository

**Steps:**
1. Navigate to the project directory
2. Initialize Git repository: `git init`
3. Check status: `git status`

**Commands:**
```bash
cd /path/to/BITS_SGA
git init
git status
```

### 1b. Git Commands Demonstration

#### git init
**Purpose:** Initializes a new Git repository in the current directory.
```bash
git init
```
**Output:** Creates a `.git` directory with repository metadata.

#### git status
**Purpose:** Shows the working tree status (untracked, modified, staged files).
```bash
git status
```
**Output:** Lists files that are untracked, modified, or staged for commit.

#### git add
**Purpose:** Stages files for commit.
```bash
git add .                    # Add all files
git add index.html          # Add specific file
git add *.html              # Add all HTML files
```
**Output:** Files are staged and ready to be committed.

#### git commit
**Purpose:** Records changes to the repository with a message.
```bash
git commit -m "Initial commit: Add web application files"
```
**Output:** Creates a commit with a unique hash and commit message.

#### git log
**Purpose:** Shows commit history.
```bash
git log                      # Full log
git log --oneline           # Compact one-line format
git log --graph --oneline   # Visual graph representation
```
**Output:** Displays commit history with author, date, and messages.

#### git branch
**Purpose:** Lists, creates, or deletes branches.
```bash
git branch                   # List all branches
git branch feature-branch   # Create new branch
git branch -d feature-branch # Delete branch
```
**Output:** Shows current branch (marked with *) and all available branches.

#### git switch
**Purpose:** Switches to a different branch.
```bash
git switch feature-branch    # Switch to existing branch
git switch -c new-branch    # Create and switch to new branch
git switch main             # Switch back to main branch
```
**Output:** Changes the working directory to the selected branch.

### 1c. GitHub Integration

**Steps:**
1. Create a GitHub account (if you don't have one)
2. Create a new repository on GitHub (don't initialize with README)
3. Add remote origin: `git remote add origin https://github.com/username/repo-name.git`
4. Push to GitHub: `git push -u origin main`

**Commands:**
```bash
# Add remote repository
git remote add origin https://github.com/yourusername/your-repo.git

# Verify remote
git remote -v

# Push to GitHub
git push -u origin main
```

**Screenshots needed:**
- GitHub repository creation page
- Terminal showing successful push
- GitHub repository page showing files

## Question 2: Docker Containerization

### 2a. Custom Docker Image

**Dockerfile Explanation:**
- Uses `nginx:alpine` as base image (lightweight web server)
- Copies HTML files to nginx html directory
- Exposes port 80 for web traffic
- Starts nginx server

### 2b. Docker Image Creation Steps

**Commands:**
```bash
# Build the Docker image
docker build -t devops-assignment:latest .

# Tag image for Docker Hub (replace username with your Docker Hub username)
docker tag devops-assignment:latest your-dockerhub-username/devops-assignment:latest

# Verify image was created
docker images
```

**Screenshots needed:**
- Terminal showing `docker build` command and output
- Terminal showing `docker images` listing the new image

### 2c. Push to Docker Hub

**Prerequisites:**
1. Create Docker Hub account at https://hub.docker.com
2. Login to Docker Hub: `docker login`

**Commands:**
```bash
# Login to Docker Hub
docker login

# Push image to Docker Hub
docker push your-dockerhub-username/devops-assignment:latest
```

**Screenshots needed:**
- Terminal showing successful login
- Terminal showing `docker push` command and output
- Docker Hub repository page showing the pushed image

### 2d. Container Deployment Demonstration

**Commands:**
```bash
# Run container locally
docker run -d -p 8080:80 --name devops-web your-dockerhub-username/devops-assignment:latest

# Check running containers
docker ps

# View container logs
docker logs devops-web

# Stop container
docker stop devops-web

# Remove container
docker rm devops-web
```

**Access the application:**
- Open browser and navigate to: `http://localhost:8080`
- You should see the home page

**Screenshots needed:**
- Terminal showing `docker run` command
- Terminal showing `docker ps` with running container
- Browser screenshot showing the web application running

## Submission Checklist

- [ ] Screenshots of all Git commands (init, status, add, commit, log, branch, switch)
- [ ] Screenshots of GitHub repository and push process
- [ ] Dockerfile content
- [ ] Screenshots of Docker build process
- [ ] Screenshots of Docker Hub repository
- [ ] Screenshots of running container and web application
- [ ] All source files (HTML pages, Dockerfile)
- [ ] GitHub repository link
- [ ] Docker Hub repository link
- [ ] Compiled Word/PDF document with all screenshots and explanations

## Notes

- Replace `your-dockerhub-username` with your actual Docker Hub username
- Replace `your-repo` with your actual GitHub repository name
- All commands should be run from the project root directory
- Ensure Docker is running before building images
- Ensure you're logged into Docker Hub before pushing images

