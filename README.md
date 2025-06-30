# Git and GitHub Session Notes

git was created by Linus Torvalds, the creator of Linux, when there was
a need for free and open-source version control system for development
of linux source tree. GitHub is, as its name implies, a hub of git
repositories, or "repo(s)", each of which contain source code tracked with git.

git allows for tracking changes and making edits safely maintaining history of
updates along with rollback features to move back to prior state of repository.

GitHub allows sharing code and collaboration including letting others review changes.

## Setup Steps

-   Create account on GitHub

-   Git Bash installation for Windows from
    [https://git-scm.com/download/win](https://git-scm.com/download/win)

-   Install ensuring git command is accessible from Powershell and Command Prompt

-   Open Powershell as administrator

-   Add configurations for git

    ```
    git config --global user.name "[username]"
    git config --global user.email "[valid-email]" # can also be GitHub noreply email
    git config --global color.ui auto
    ```

-   Generate public/private keypair (optionally use passphrase)

    ```
    ssh-keygen -t ed25519 -C "[valid-email]"
    # or use ssh-keygen -t rsa -b 4096 -C "[valid-email]" if above fails
    ```

-   Setup SSH Agent

    ```
    Start-Service ssh-agent
    ssh-add C:\path\to\your\ssh\key\id_ed25519
    Set-Service ssh-agent -StartupType Automatic
    ```

-   Add public key to GitHub settings (`Settings > SSH and GPG keys > Add`)

    ```
    cat C:\path\to\your\ssh\key\id_ed25519.pub
    ```

-   Test connection
    ```
    ssh -T git@github.com
    ```

## Basic Workflow and Commands

Most important commands are init, add, status, commit, push, pull, branch.

![Git Workflow](./git_workflow.jpg)

Cheatsheet:

![Cheatsheet 1](./git_cheatsheet_1.jpg)
![Cheatsheet 2](./git_cheatsheet_2.jpg)

Cheatsheet by GitHub Education:

[git cheatsheet by GitHub](https://education.github.com/git-cheat-sheet-education.pdf)

## Collaboration in Team

Teams can collaborate by keeping local copy on each team member's machine
and maintaining central repository on GitHub for sync.

### Contributors vs Pull Requests

There are two ways to collaborate on the same repository. Adding contributors
or handling pull requests. Added contributors have direct access and can make
changes without requiring any review from repository owner/maintainers. In contrast, pull
request gives the repository maintainers control to review changes, suggest
modifications and ultimately the authority on whether to accept or decline
change request.
