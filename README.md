Git Commands
============

## Translated Versions
- [Versão em português](READMEpt.md)
- [Versión en español](READMEes.md)
- [Türkçe versiyon](READMEtr.md)
- [বাংলা সংস্করণ](READMEbn.md)

___

_A list of my commonly used Git commands_


*If you are interested in my Git aliases, have a look at my `.bash_profile`, found here: https://github.com/joshnh/bash_profile/blob/master/.bash_profile*

--

<ul>
<li>
<p><code>git init</code> initializes a brand new Git repository and begins tracking an existing directory. It adds a hidden subfolder within the existing directory that houses the internal data structure required for version control.</p>
</li>
<li>
<p><code>git clone</code> creates a local copy of a project that already exists remotely. The clone includes all the project's files, history, and branches.</p>
</li>
<li>
<p><code>git add</code> stages a change. Git tracks changes to a developer's codebase, but it's necessary to stage and take a snapshot of the changes to include them in the project's history. This command performs staging, the first part of that two-step process. Any changes that are staged will become a part of the next snapshot and a part of the project's history. Staging and committing separately gives developers complete control over the history of their project without changing how they code and work.</p>
</li>
<li>
<p><code>git commit</code> saves the snapshot to the project history and completes the change-tracking process. In short, a commit functions like taking a photo. Anything that's been staged with <code>git add</code> will become a part of the snapshot with <code>git commit</code>.</p>
</li>
<li>
<p><code>git status</code> shows the status of changes as untracked, modified, or staged.</p>
</li>
<li>
<p><code>git branch</code> shows the branches being worked on locally.</p>
</li>
<li>
<p><code>git merge</code> merges lines of development together. This command is typically used to combine changes made on two distinct branches. For example, a developer would merge when they want to combine changes from a feature branch into the main branch for deployment.</p>
</li>
<li>
<p><code>git pull</code> updates the local line of development with updates from its remote counterpart. Developers use this command if a teammate has made commits to a branch on a remote, and they would like to reflect those changes in their local environment.</p>
</li>
<li>
<p><code>git push</code> updates the remote repository with any commits made locally to a branch.</p>
</li>
</ul>



<h3 id="example-start-a-new-repository-and-publish-it-to-github"><a aria-hidden="" tabindex="-1" class="doctocat-link" href="#example-start-a-new-repository-and-publish-it-to-github"><svg aria-hidden="" role="img" class="octicon-link" viewBox="0 0 16 16" width="16" height="16" fill="currentColor" style="display:inline-block;user-select:none;vertical-align:middle"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>Example: Start a new repository and publish it to GitHub</h3>
<p>First, you will need to create a new repository on GitHub. For more information, see "<a href="/en/get-started/quickstart/hello-world">Hello World</a>." <strong>Do not</strong> initialize the repository with a README, .gitignore or License file. This empty repository will await your code.</p>
<pre><code class="hljs language-bash"><span class="hljs-comment"># create a new directory, and initialize it with git-specific functions</span>
git init my-repo

<span class="hljs-comment"># change into the `my-repo` directory</span>
<span class="hljs-built_in">cd</span> my-repo

<span class="hljs-comment"># create the first file in the project</span>
<span class="hljs-built_in">touch</span> README.md

<span class="hljs-comment"># git isn't aware of the file, stage it</span>
git add README.md

<span class="hljs-comment"># take a snapshot of the staging area</span>
git commit -m <span class="hljs-string">"add README to initial commit"</span>

<span class="hljs-comment"># provide the path for the repository you created on github</span>
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPOSITORY-NAME.git

<span class="hljs-comment"># push changes to github</span>
git push --set-upstream origin main
</code></pre>






### Setting your username in Git

Changing the name associated with your Git commits using git config will only affect future commits and will not change the name used for past commits.


| Command | Description |
| ------- | ----------- |
| ` git config --global user.name "Mona Lisa"` | Changing the name associated with your Git commits using git config will only affect future commits and will not change the name used for past commits. |




### Getting & Creating Projects

| Command | Description |
| ------- | ----------- |
| `git init` | Initialize a local Git repository |
| `git clone ssh://git@github.com/[username]/[repository-name].git` | Create a local copy of a remote repository |

### Basic Snapshotting

| Command | Description |
| ------- | ----------- |
| `git status` | Check status |
| `git add [file-name.txt]` | Add a file to the staging area |
| `git add -A` | Add all new and changed files to the staging area |
| `git commit -m "[commit message]"` | Commit changes |
| `git rm -r [file-name.txt]` | Remove a file (or folder) |

### Branching & Merging

| Command | Description |
| ------- | ----------- |
| `git branch` | List branches (the asterisk denotes the current branch) |
| `git branch -a` | List all branches (local and remote) |
| `git branch [branch name]` | Create a new branch |
| `git branch -d [branch name]` | Delete a branch |
| `git push origin --delete [branch name]` | Delete a remote branch |
| `git checkout -b [branch name]` | Create a new branch and switch to it |
| `git checkout -b [branch name] origin/[branch name]` | Clone a remote branch and switch to it |
| `git branch -m [old branch name] [new branch name]` | Rename a local branch |
| `git checkout [branch name]` | Switch to a branch |
| `git checkout -` | Switch to the branch last checked out |
| `git checkout -- [file-name.txt]` | Discard changes to a file |
| `git merge [branch name]` | Merge a branch into the active branch |
| `git merge [source branch] [target branch]` | Merge a branch into a target branch |
| `git stash` | Stash changes in a dirty working directory |
| `git stash clear` | Remove all stashed entries |

### Sharing & Updating Projects

| Command | Description |
| ------- | ----------- |
| `git push origin [branch name]` | Push a branch to your remote repository |
| `git push -u origin [branch name]` | Push changes to remote repository (and remember the branch) |
| `git push` | Push changes to remote repository (remembered branch) |
| `git push origin --delete [branch name]` | Delete a remote branch |
| `git pull` | Update local repository to the newest commit |
| `git pull origin [branch name]` | Pull changes from remote repository |
| `git remote add origin ssh://git@github.com/[username]/[repository-name].git` | Add a remote repository |
| `git remote set-url origin ssh://git@github.com/[username]/[repository-name].git` | Set a repository's origin branch to SSH |

### Inspection & Comparison

| Command | Description |
| ------- | ----------- |
| `git log` | View changes |
| `git log --summary` | View changes (detailed) |
| `git log --oneline` | View changes (briefly) |
| `git diff [source branch] [target branch]` | Preview changes before merging |
