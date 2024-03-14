# Learn git
## The Basics
### 1. `git add`

- **What it does**: Adds changes in your working directory to the staging area.
- **Analogy**: Imagine you're packing a box for shipping. Adding files is like selecting items you want to send and placing them into the box. They're not sent yet; they're just ready and waiting.
- **Key point**: It doesn't save any changes permanently. It just marks files for inclusion in the next commit.

### 2. `git commit`

- **What it does**: Saves your staged changes to the local repository.
- **Analogy**: Once you're happy with what’s in the box (staging area), you seal it up (commit). The box is still with you; it’s not sent to the recipient yet.
- **Key point**: Committing takes your staged changes and makes a permanent snapshot of those changes in your repository, tagged with a unique identifier (a commit hash).

### 3. `git push`

- **What it does**: Sends your committed changes to a remote repository.
- **Analogy**: Now you're ready to ship the box to its destination. Pushing is like sending the box off; it travels to the remote location (like a warehouse or the recipient’s address).
- **Key point**: It uploads your local commits to the remote repository, making your changes available to others or syncing with a backup location.

### How They Differ:

- **Scope**: `add` prepares files for a commit, `commit` records the snapshot of the changes locally, and `push` shares the committed changes with others or uploads to a remote repository.
- **Visibility**: Changes added with `git add` are not visible to others yet. Commits are saved locally and become part of your project's history, but they're still not visible to others until you `push` them.
- **Frequency**: You might `add` multiple times before committing, creating a commit once you’re satisfied with your bundled changes. You might `commit` several times before deciding to `push` your changes to the remote repository, especially in a collaborative project.

Remember, `git add` and `git commit` are local operations affecting your local repository, while `git push` interacts with a remote repository.

### Simplified Git Functions

- **`git add`**: This command is like telling Git, "Hey, I’ve made some changes or added new files/folders that I think are important. Can you please keep an eye on them?" Essentially, it stages your changes and new files for a commit. This is your way of selecting which changes you want to save in your next snapshot (commit).

- **`git commit`**: After adding your changes, using `git commit` is like saying, "Okay, Git, I'm sure about these changes. Let's save a snapshot of this state." A commit is like a milestone, marking a specific point in your project's history. You also add a message to describe what you did in this snapshot, helping future you or others understand what happened and why.

- **`git push`**: This command is used to upload your local repository content to a remote repository. Imagine you’ve been working on a document on your computer, and now you want to share it with your team by uploading it to a shared drive. That’s what `git push` does; it takes your commits (those snapshots you saved) and sends them to the remote repository (like GitHub) so others can see and work with your changes.

### Adding Folders to a Git Repository

Is it better to add folders locally or through the GitHub GUI:

- **Locally**: Generally, it's more efficient and flexible to add folders and files to your Git repository locally, especially if you’re working with multiple files or the changes are part of your development workflow. You create or update files/folders in your project directory, use `git add` to stage these changes, and then `git commit` and `git push` to save and share these changes. Git does not track empty folders, so to add a new folder, it needs to contain at least one file. A common practice is to add a `.gitkeep` file in empty directories you wish to track.

- **GitHub GUI**: Adding files or making changes through GitHub’s web interface can be convenient for quick fixes, small changes, or if you’re not comfortable with command-line tools. However, this method is more cumbersome for managing larger sets of files or for integrating changes into your local development process. It's more suited to editing individual files rather than managing entire folders.

### Recommendation

For development purposes, it's generally recommended to manage your project locally using Git commands and then sync these changes to GitHub with `git push`. This approach gives you more control over your project's structure, supports working offline, and integrates better with your local development tools and workflows.


## Simplified Git for Beginners

### Git Setup

- **Configure your Git username and email** (this is important because every Git commit uses this information):
  ```bash
  git config --global user.name "Your Name"
  git config --global user.email "youremail@example.com"
  ```

### Starting with Git

- **Initialize a new Git repository**:
  ```bash
  git init
  ```
  
- **Clone an existing repository**:
  ```bash
  git clone https://github.com/username/repository.git
  ```

### Basic Git Commands

- **Check the status of your files** (see which files are staged, unstaged, or untracked):
  ```bash
  git status
  ```

- **Track new files or stage changes** (add files or changes to the staging area):
  ```bash
  git add filename
  git add .
  ```
  Use `filename` to add a specific file, or use `.` to add all new and changed files.

- **Commit your staged content** (save your staged changes as a new commit snapshot):
  ```bash
  git commit -m "Descriptive message here"
  ```

- **Push your changes to the remote repository**:
  ```bash
  git push origin branch-name
  ```
  Replace `branch-name` with the branch you want to push.

- **Pull the latest changes from the remote repository**:
  ```bash
  git pull
  ```

### Branching in Git

- **Create a new branch**:
  ```bash
  git branch branch-name
  ```

- **Switch to a different branch**:
  ```bash
  git checkout branch-name
  ```

- **Create a new branch and switch to it**:
  ```bash
  git checkout -b branch-name
  ```

- **Merge a branch into the active branch**:
  ```bash
  git merge branch-name
  ```

- **Delete a branch**:
  ```bash
  git branch -d branch-name
  ```

### Viewing Changes

- **View changes to files** (see what's different from your last commit):
  ```bash
  git diff
  ```

- **View the commit history**:
  ```bash
  git log
  ```

- **View a summary of the commit history with one line per commit**:
  ```bash
  git log --oneline
  ```

### Undoing Changes

- **Undo changes in a specific file** (revert a file to the last committed state):
  ```bash
  git checkout -- filename
  ```

- **Reset your current branch to a specific commit** (dangerous if you're not sure, as it erases history):
  ```bash
  git reset --hard commit-hash
  ```

- **Revert a commit by creating a new commit with contrary changes**:
  ```bash
  git revert commit-hash
  ```

### Collaboration and Updates

- **Fetch updates from the remote repository** (does not merge them):
  ```bash
  git fetch
  ```

- **Integrate changes from a remote repository into your current branch**:
  ```bash
  git pull
  ```

- **Update your local repository to the newest commit** (fetch and merge):
  ```bash
  git pull origin branch-name
  ```