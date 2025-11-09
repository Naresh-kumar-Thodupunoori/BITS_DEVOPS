# Grading Checklist for Support Staff

This document helps verify student submissions against assignment requirements.

## Question 1: Git Version Control (10 Marks)

### 1a. Local Git Repository (2 Marks) ✓/✗
**Check for:**
- [ ] Simple web application with 2-3 HTML pages
- [ ] Git repository initialized (`git init`)
- [ ] Screenshot showing `git init` command
- [ ] Screenshot showing `git status` with untracked files

**Expected Files:**
- index.html
- about.html
- contact.html (or similar)
- Dockerfile

**Acceptable:** Any 2-3 HTML pages that form a simple web application

---

### 1b. Git Commands Demonstration (6 Marks) ✓/✗

**Required Commands (1 mark each if all shown correctly):**

#### git init ✓/✗
- [ ] Screenshot showing command execution
- [ ] Explanation of what it does
- **Expected Output:** "Initialized empty Git repository..."

#### git status ✓/✗
- [ ] Screenshot showing command execution
- [ ] Explanation of what it shows
- **Expected Output:** Lists untracked/modified/staged files

#### git add ✓/✗
- [ ] Screenshot showing `git add` command
- [ ] Screenshot showing `git status` after add (files staged)
- [ ] Explanation of staging files
- **Expected Output:** Files move from "untracked" to "staged"

#### git commit ✓/✗
- [ ] Screenshot showing `git commit -m "message"`
- [ ] Explanation of creating snapshot
- **Expected Output:** Commit hash and message confirmation

#### git log ✓/✗
- [ ] Screenshot showing `git log` or `git log --oneline`
- [ ] Explanation of viewing history
- **Expected Output:** List of commits with hashes, authors, dates

#### git branch ✓/✗
- [ ] Screenshot showing `git branch` listing branches
- [ ] Screenshot showing branch creation
- [ ] Explanation of branch management
- **Expected Output:** List of branches, current branch marked with *

#### git switch ✓/✗
- [ ] Screenshot showing `git switch branch-name`
- [ ] Screenshot showing branch change confirmation
- [ ] Explanation of switching branches
- **Expected Output:** "Switched to branch 'branch-name'"

**Partial Credit:** If student shows 5-6 commands correctly, award 5 marks. If 3-4 commands, award 3 marks.

---

### 1c. GitHub Integration (2 Marks) ✓/✗
**Check for:**
- [ ] GitHub repository created
- [ ] Screenshot of GitHub repository page
- [ ] Screenshot of `git remote add origin` command
- [ ] Screenshot of `git push` command showing success
- [ ] Link to GitHub repository provided
- [ ] Repository contains the HTML files and Dockerfile

**Acceptable Evidence:**
- GitHub repository URL (public or shared)
- Screenshots showing successful push
- Repository visible on GitHub with project files

**Partial Credit:** If repository created but push not shown, award 1 mark.

---

## Question 2: Docker Containerization (10 Marks)

### 2a. Custom Docker Image (2 Marks) ✓/✗
**Check for:**
- [ ] Dockerfile provided in submission
- [ ] Dockerfile contains:
  - [ ] FROM instruction (base image)
  - [ ] COPY or ADD instruction (copying files)
  - [ ] EXPOSE instruction (port declaration)
  - [ ] CMD or ENTRYPOINT (start command)
- [ ] Brief description of application
- [ ] Application is simple but functional (e.g., web app, Python script, etc.)

**Acceptable Dockerfiles:**
- Web application (nginx, apache)
- Python application (Flask, simple script)
- Node.js application
- Any simple application that demonstrates containerization

**Partial Credit:** If Dockerfile exists but incomplete, award 1 mark.

---

### 2b. Docker Image Creation Steps (2 Marks) ✓/✗
**Check for:**
- [ ] Screenshot of `docker build` command
- [ ] Screenshot showing build process (layers being built)
- [ ] Screenshot of `docker images` showing the created image
- [ ] Image name visible in output
- [ ] Build completed successfully (no errors)

**Expected Commands:**
```bash
docker build -t image-name:tag .
docker images
```

**Partial Credit:** If build shown but incomplete, award 1 mark.

---

### 2c. Push to Docker Hub (3 Marks) ✓/✗
**Check for:**
- [ ] Screenshot of `docker login` command
- [ ] Screenshot of `docker tag` command (tagging for Docker Hub)
- [ ] Screenshot of `docker push` command showing upload progress
- [ ] Screenshot of Docker Hub repository page showing the image
- [ ] Link to Docker Hub repository provided
- [ ] Image visible on Docker Hub

**Expected Commands:**
```bash
docker login
docker tag local-image:tag username/image-name:tag
docker push username/image-name:tag
```

**Partial Credit:**
- Login + tag shown: 1 mark
- Login + tag + push shown: 2 marks
- All + Docker Hub screenshot: 3 marks

---

### 2d. Container Deployment Demonstration (3 Marks) ✓/✗
**Check for:**
- [ ] Screenshot of `docker run` command
- [ ] Screenshot of `docker ps` showing running container
- [ ] Screenshot of application running (browser or terminal output)
- [ ] Container is actually running (not just created)
- [ ] Application is accessible and functional

**Expected Commands:**
```bash
docker run -d -p host-port:container-port image-name
docker ps
# Application accessible at localhost:port
```

**For Web Applications:**
- Browser screenshot showing the web page
- Multiple pages shown (if applicable)

**For CLI Applications:**
- Terminal output showing application running
- Output visible and correct

**Partial Credit:**
- Container run command shown: 1 mark
- Container running + application visible: 2 marks
- All with proper screenshots: 3 marks

---

## Overall Submission Quality

### Documentation ✓/✗
- [ ] All screenshots compiled into single Word/PDF document
- [ ] Captions/explanations under each screenshot
- [ ] Clear organization and structure
- [ ] Professional presentation

### Source Files ✓/✗
- [ ] HTML pages included
- [ ] Dockerfile included
- [ ] Any additional application files included
- [ ] Files are functional and complete

### Links ✓/✗
- [ ] GitHub repository link provided
- [ ] Docker Hub repository link provided
- [ ] Links are accessible and public/shared

### File Organization ✓/✗
- [ ] Files organized in folder
- [ ] Folder compressed to .zip
- [ ] All required files present

---

## Common Issues and How to Handle

### Issue: Missing Screenshots
**Action:** Check if student provided terminal logs or text descriptions. Award partial credit if commands are documented but not screenshotted.

### Issue: Incomplete Git Commands
**Action:** If student shows 5-6 out of 7 commands correctly, award proportional marks (5-6 marks out of 6).

### Issue: Docker Image Not Pushed
**Action:** If build shown but push missing, award marks for 2a and 2b, but not 2c.

### Issue: Container Not Running
**Action:** If `docker run` shown but no evidence of running application, award 1 mark for attempt.

### Issue: Wrong Commands
**Action:** If student uses incorrect syntax but demonstrates understanding, award partial credit. If completely wrong, no marks.

### Issue: Screenshots Unclear
**Action:** If screenshots are blurry but commands visible, accept. If completely unreadable, request clarification or award partial credit.

### Issue: Repository Links Not Working
**Action:** Check if repository is private. If private but shared with instructor, accept. If completely inaccessible, award partial credit for attempt.

---

## Grading Scale Summary

| Component | Max Marks | Criteria |
|-----------|-----------|----------|
| 1a. Local Git Repo | 2 | HTML pages + git init |
| 1b. Git Commands | 6 | 7 commands demonstrated |
| 1c. GitHub Integration | 2 | Repo created + pushed |
| 2a. Docker Image | 2 | Dockerfile + description |
| 2b. Build Steps | 2 | Build command + output |
| 2c. Docker Hub Push | 3 | Login + tag + push + screenshot |
| 2d. Container Run | 3 | Run + ps + application visible |
| **Total** | **20** | |

---

## Quick Verification Commands

If you need to verify a student's work:

### Check Git Repository
```bash
cd student-submission-folder
git log --oneline  # Should show commits
git remote -v      # Should show GitHub remote
```

### Check Docker Image
```bash
docker images | grep student-image-name
docker pull student-username/image-name  # If on Docker Hub
docker run -d -p 8080:80 student-username/image-name
# Check http://localhost:8080
```

---

## Notes for Graders

1. **Be lenient with screenshots:** If commands are visible and correct, accept even if formatting is imperfect.

2. **Partial credit is important:** Students may miss one step but demonstrate understanding of the concept.

3. **Focus on learning outcomes:** The goal is to ensure students understand Git and Docker basics, not perfection.

4. **Check for plagiarism:** If multiple submissions are identical, investigate further.

5. **Verify links work:** Test GitHub and Docker Hub links to ensure they're accessible.

6. **Document issues:** Note any problems in feedback for students to improve.

---

## Sample Correct Submission

A perfect submission should include:

1. **Word/PDF Document with:**
   - Title page
   - Section 1: Git commands (7 screenshots with explanations)
   - Section 2: GitHub integration (3-4 screenshots)
   - Section 3: Docker build (2-3 screenshots)
   - Section 4: Docker Hub (3-4 screenshots)
   - Section 5: Container running (3-4 screenshots)
   - Links section

2. **Source Files Folder:**
   - index.html
   - about.html
   - contact.html (or similar)
   - Dockerfile
   - README.md (optional but good practice)

3. **Working Links:**
   - GitHub: https://github.com/username/repo
   - Docker Hub: https://hub.docker.com/r/username/image

---

**End of Grading Checklist**

