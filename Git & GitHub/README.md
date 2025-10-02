
⏳ **Version Control**: A system that keeps track of changes to files over time. This allows developers to go back to earlier versions, work together efficiently, and handle different versions of code. It helps prevent data loss and ensures teamwork in software development runs smoothly.

📦 **Repo (Repository)**: 📁: A folder where Git has been initialized.

Think of this as the main project folder. A "repo" is a directory where Git has been activated to start tracking changes.

🌿 **Git**: A powerful tool installed on your local machine that acts as a distributed version control system. It's the core engine for tracking code changes, managing branches, and allowing developers to work efficiently on their own versions of a project.

☁️ **GitHub**: A cloud-based platform that acts as a central hub for your Git repositories. It brings the power of Git to the cloud, enabling seamless collaboration, code sharing, project management and keep track of changes efficiently among developers from anywhere in the world.

**🔄 Difference Between Git & GitHub**

- **Git** 💻:
  - Works locally on your computer.
  - Tracks changes in your folders and files.
  - Helps in organizing code with the use of branches.
- **GitHub** 🌐:
  - A cloud platform that hosts your local repositories online.
  - Allows anyone with the repository link to access the project and contribute changes.

**💻 Master List of Git Commands**

Here is a more colorful and organized list of the essential Git commands.

**⚙️ One-Time Setup & Configuration**

You typically only need to run these commands once when you first set up Git on your computer.

- git config --global user.name "Your Name"
  - 👤 **Action**: Sets the name that will be attached to your commits and tags.
- git config --global user.email "<your-email@example.com>"
  - 📧 **Action**: Sets the email address that will be attached to your commits.

**🔍 Inspection & Utility Commands**

Use these commands to check the status of your repository and view its history.

- git status
  - 📊 **Action**: Shows the current state of your repository, including which files are modified, staged, or untracked.
- git log
  - 📜 **Action**: Displays the commit history, showing who made changes and when.
- ls -a
  - 👀 **Action**: A handy terminal command (not a Git command) to list all files in the current directory, including hidden ones like the .git folder.

**🌊 Core Workflow Commands (Pushing to GitHub)**

This is the main cycle you'll use to save your work locally and upload it to GitHub.

- git add . or git add --all
  - ✨ **Action**: Adds all new and modified files to the "staging area," preparing them for a snapshot.
- git commit -m 'Your Message'
  - 📸 **Action**: Takes a snapshot of the staged files and saves it to your local repository's history with a descriptive message.
- git remote add origin &lt;repoLink&gt;
  - 🔗 **Action**: Connects your local repository to a remote one on GitHub. You only need to do this once per project.
- git push origin &lt;branchName&gt;
  - 📤 **Action**: Uploads your committed changes from your local branch to the remote repository (like GitHub).
- git pull origin &lt;branchName&gt;
  - 📥 **Action**: Fetches the latest updates from a remote repository and merges them into your current local branch.

**🌿 Branching Commands**

Branches allow you to work on different features without affecting the main codebase.

- git branch
  - 🌳 **Action**: Lists all the branches in your local repository.
- git branch &lt;branch-name&gt;
  - 🌱 **Action**: Creates a brand new local branch.
- git checkout &lt;branch-name&gt; or git switch &lt;branch-name&gt;
  - 🚶‍♀️ **Action**: Switches your current working directory to the specified branch.
- git checkout -b &lt;branch-name&gt; or git switch -c &lt;branch-name&gt;
  - 🏃‍♀️ **Action**: A handy shortcut that creates a new branch and immediately switches to it.
- git merge &lt;branch-name&gt;
  - 🤝 **Action**: Joins the changes from a specified branch into your current branch.
- git branch -d &lt;branch-name&gt;
  - 🗑️ **Action**: Deletes a local branch (a safety check prevents deletion if it's not fully merged).
- git branch -D &lt;branch-name&gt;
  - 💥 **Action**: **Force deletes** a local branch, even if it hasn't been merged.
- git push origin --delete &lt;branch-name&gt;
  - 🔥 **Action**: Deletes a branch from your remote repository (GitHub).
- git branch -m &lt;old-name&gt; &lt;new-name&gt;
  - 🏷️ **Action**: Renames a local branch.
- git branch -r
  - 📡 **Action**: Lists all the remote branches that your local repository is aware of.
