# Hosting a Resume with Pelican and GitHub Pages

## Purpose
This README provides a step-by-step guide for creating and hosting a resume website using **Pelican**, a static site generator, and **GitHub Pages**, a free hosting service offered by Github. It follows Andrew Etter’s principles from *Modern Technical Writing* by demonstrating:
- **Lightweight markup** (Markdown) for simplicity and maintainability.
- **Distributed version control** (Git) for collaboration and tracking.
- **Static site generation** (Pelican) for efficiency, security, and performance.

This guide is particularly useful for:
- **Students and professionals** who want to showcase their resumes online in a structured, efficient, and version-controlled way.
- **Beginners in static site hosting** who need clear, actionable instructions on deploying a personal website using Pelican and GitHub Pages.

By following this guide, you will learn how to structure, format, and deploy a **technical resume** using modern documentation tools.

## Website and Repository
- **Live Website**: [Meshvi's Resume](https://meshvii.github.io/COMP2600_A2_PatelMeshvi/)
- **GitHub Repository**: [COMP2600_A2_PatelMeshvi](https://github.com/meshvii/COMP2600_A2_PatelMeshvi)

## Project Structure
The recommended repository structure for **Pelican + GitHub Pages**:

```
COMP2600_A2_PatelMeshvi/
│── content/                  # Markdown files for pages (resume, blog posts, etc.)
│   ├── Resume.md             # Your resume formatted in Markdown
│
│── output/                    # Generated static HTML files (ignored in Git)
│
│── pelicanconf.py              # Pelican site configuration
│
│── publishconf.py              # Publishing-specific configuration
│
│── Makefile                    # Automates Pelican commands (optional)
│
│── tasks.py                     # Automation script (optional)
│
│── README.md                    # Project documentation
```
### **Key Features**
- **Markdown-based content** is stored in `content/`.
- **Generated HTML files** are placed in `output/` (should be **ignored in Git**).
- **Configuration settings** are managed via `pelicanconf.py` and `publishconf.py`.
- **Automation tools** like `Makefile` can simplify development.

## Why Use Pelican and GitHub Pages?

Pelican and GitHub Pages align with modern technical documentation best practices:

 **Lightweight & Fast** – Generates static files, reducing server dependencies.  
 **Secure** – No backend vulnerabilities; purely static files.  
 **Version Controlled** – Tracks changes with Git.  
 **Customizable** – Themes, plugins, and Markdown extensions.  
 **Easy Deployment** – Push changes to GitHub, and they are live instantly.  

## Using Markdown for Your Resume
Markdown is a **lightweight markup language** that simplifies content formatting.

### **Benefits of Markdown**
- **Readable & Simple** – No need for complex formatting.
- **Portable** – Works across multiple platforms.
- **Ideal for Version Control** – Text-based changes are easy to track.
- **Flexible** – Supports headings, lists, links, images, and code snippets.

### Resume in Markdown
Below is an example of how your resume should be formatted in Markdown for Pelican:

You can use - [Dillinger](https://dillinger.io/) for your markdown file generation.

```markdown
Title: My Resume
Date: 2025-03-05
Category: Resume
Tags: pelican, github-pages
Authors: Meshvi Patel
Summary: A static site hosting my resume.
# Meshvi Patel
Winnipeg, MB, Canada  
Email: [your.email@example.com](mailto:your.email@example.com)  
LinkedIn: [your-profile](https://linkedin.com/in/your-profile)  
GitHub: [your-github](https://github.com/your-github)
```
### **Format a Resume in Markdown**
1. **Use Markdown elements** – Structure your resume using headings, lists, hyperlinks, bold/italic text, and optionally tables or images.
2. **Choose content** – Use your own resume or find an example online, such as from [Overleaf’s CV Gallery](https://www.overleaf.com/gallery/tagged/cv).
3. **Focus on content, not layout** – Markdown is for structuring content, not replicating graphical layouts. Keep formatting minimal and readable.
4. **Save the resume** – Store it as `Resume.md` in your project’s `content/` directory.
5. **Preview your resume** – Open the Markdown file in a live preview editor or use a text editor with Markdown support.

This step ensures that your resume is cleanly structured before integrating it into the Pelican static site.

## Prerequisites
Before proceeding, ensure you have the following tools installed and set up:

- **Python** – Required for Pelican installation and site generation. Download the latest stable version from [python.org](https://www.python.org/) and ensure it is added to your system path.
- **Pelican** – Install Pelican along with Markdown support using:
  ```bash
  python -m pip install "pelican[markdown]"
  ```
  This ensures that Pelican can process Markdown files and generate static content.
- **Git** – Essential for version control and deployment to GitHub Pages. Install Git from [git-scm.com](https://git-scm.com/) and configure it with your GitHub credentials.
- **GitHub Account** – Required to host the resume site. If you do not have one, create an account at [GitHub](https://github.com/).
- **ghp-import** – A tool to simplify deploying static sites to GitHub Pages. Install it using:
  ```bash
  python -m pip install ghp-import
  ```
- **Text Editor or IDE** – Use a code editor such as Visual Studio Code, PyCharm, or Sublime Text to efficiently edit and manage your Markdown and Pelican configuration files.

Once these tools are installed, you are ready to begin setting up and deploying your Pelican-based resume site on GitHub Pages.

## Instructions: Deploying Your Resume with Pelican & GitHub Pages
Andrew Etter recommends **static site generation and version control** to ensure maintainability, security, and ease of updates. The following instructions follow these principles.

### **Step 1: Install and Configure Pelican**
1. **Use a lightweight markup language** *(Etter recommends Markdown for documentation clarity).* Install Python, required for Pelican, from [python.org](https://www.python.org/).
2. **Install Pelican and Markdown support** *(Etter advises using static site generators like Pelican for efficiency and security).* Run:
   ```bash
   python -m pip install "pelican[markdown]"
   ```
3. **Initialize a new Pelican project** 
* Run:
   ```bash
   pelican-quickstart
   ```
   - Provide details like site title, author name, and language.
   - Choose to enable GitHub Pages for hosting and provide your github-repo.
   - Provide the timezone (America/Winnipeg)

4. **Add Your Resume** – Place your Markdown resume file in the `content/` directory.
5. **Generate the static site** *(Following Etter’s recommendation to avoid dynamic sites, ensuring security and speed).* Run:
   ```bash
   pelican content
   ```
6. **Preview the site locally** *(Etter suggests frequent publishing to ensure continuous updates).* Run:
   ```bash
   pelican --listen
   ```
   - Open `http://127.0.0.1:8000` in a browser.

### **Step 2: Deploy to GitHub Pages**
Etter strongly advocates for **distributed version control**, ensuring that documentation is always backed up and accessible.
1. **Initialize a Git repository** – If not already initialized:
   ```bash
   git init
   ```
2. **Add and commit changes**:
   ```bash
   git add ./
   git commit -m "Initial commit"
   ```
3. **Push to GitHub** – Replace `<username>` and `<repository>`:
   ```bash
   git remote add origin https://github.com/<username>/<repository>.git 
   git push -u origin main
   ```
4. **Deploy using `ghp-import`** *(Etter recommends automating publishing as much as possible).* Run:
   ```bash
   pelican content -s publishconf.py
   ghp-import output -b gh-pages
   git push origin gh-pages
   ```
5. **Access the hosted site** – Visit `https://<username>.github.io/<repository>/`. 

## Further Reading
- [Markdown Tutorial](https://commonmark.org/help/tutorial/)
- [Pelican Documentation](https://docs.getpelican.com/)
- [Git Basics Guide](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics)
- [GitHub Pages Guide](https://pages.github.com/)

## FAQ
### **Q: Why use Markdown instead of Word?**  
**A:** Markdown's plain text format for easy editing and compatibility.Its platform independence, making it accessible across systems and its integration with Git for version control and collaboration.

### **Q: My resume changes aren't appearing. What do I do?**  
**A:** Regenerate the site with:
   ```bash
   pelican content
   ```
   Then redeploy using:
   ```bash
   ghp-import output -b gh-pages
   git push origin gh-pages
   ```

### **Q: How do I update my resume?**  
1. Edit `content/Resume.md`.
2. Run `pelican content`.
3. Push the changes to GitHub.

---

## Credits
- **Course**: COMP 2600 – Technical Communication in Computer Science
- **Instructor**: Tristan Miller
- **Peer Review Contributors:** Om Sevak, Adwait Pujari
- **References**: *Modern Technical Writing* by Andrew Etter (2016)
- **GitHub Repository**: [COMP2600_A2_PatelMeshvi](https://github.com/meshvii/COMP2600_A2_PatelMeshvi)