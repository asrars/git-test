# Table of Contents

1. [Creating a personal access token](#accessToken)
2. [Application required commands](#applicationCommands)
3. [Detailed Explaination on some of the basic needed git commands](#explaination)


# Creating a personal access token <a name="accessToken"></a>

You should create a personal access token to use in place of a password with the command line or with the API.

>Note: If you use GitHub CLI to authenticate to GitHub on the command line, you can skip generating a personal access token and authenticate via the web browser instead. For more information about authenticating with GitHub CLI, see [gh auth login](https://cli.github.com/manual/gh_auth_login).

Personal access tokens (PATs) are an alternative to using passwords for authentication to GitHub when using the [GitHub API](https://docs.github.com/en/rest/overview/other-authentication-methods#via-oauth-and-personal-access-tokens) or the [command line](https://docs.github.com/en/github/authenticating-to-github/keeping-your-account-and-data-secure/creating-a-personal-access-token#using-a-token-on-the-command-line).

If you want to use a PAT to access resources owned by an organization that uses SAML SSO, you must authorize the PAT. For more information, see "[About authentication with SAML single sign-on](https://docs.github.com/en/github/authenticating-to-github/about-authentication-with-saml-single-sign-on)" and "[Authorizing a personal access token for use with SAML single sign-on.](https://docs.github.com/en/github/authenticating-to-github/authorizing-a-personal-access-token-for-use-with-saml-single-sign-on)"

As a security precaution, GitHub automatically removes personal access tokens that haven't been used in a year. To provide additional security, we highly recommend adding an expiration to your personal access tokens.

# Creating a token

1. [Verify your email address](https://docs.github.com/en/github/getting-started-with-github/verifying-your-email-address), if it hasn't been verified yet.
2. In the upper-right corner of any page, click your profile photo, then click **Settings**.
3. In the left sidebar, click **Developer settings**.
4. In the left sidebar, click **Personal access tokens**.
5. Click **Generate new token**.
6. Give your token a descriptive name.
7. To give your token an expiration, select the **Expiration** drop-down menu, then click a default or use the calendar picker.
8. Select the scopes, or permissions, you'd like to grant this token. To use your token to access repositories from the command line, select **repo**.
9. Click **Generate token**.
>  **Warning:** Treat your tokens like passwords and keep them secret. When working with the API, use tokens as environment variables instead of hardcoding them into your programs.

10. To use your token to authenticate to an organization that uses SAML SSO, authorize the token for use with a SAML single-sign-on organization.

# Using a token on the command line
Once you have a token, you can enter it instead of your password when performing Git operations over HTTPS.

For example, on the command line you would enter the following:

> $ git clone https://github.com/username/repo.git
> 
> Username: your_username
> 
> Password: your_token>

Personal access tokens can only be used for HTTPS Git operations. If your repository uses an SSH remote URL, you will need to [switch the remote from SSH to HTTPS](https://docs.github.com/en/github/getting-started-with-github/managing-remote-repositories/#switching-remote-urls-from-ssh-to-https).

If you are not prompted for your username and password, your credentials may be cached on your computer. You can [update your credentials in the Keychain](https://docs.github.com/en/github/getting-started-with-github/updating-credentials-from-the-macos-keychain) to replace your old password with the token.

Instead of manually entering your PAT for every HTTPS Git operation, you can cache your PAT with a Git client. Git will temporarily store your credentials in memory until an expiry interval has passed. You can also store the token in a plain text file that Git can read before every request. For more information, see "[Caching your GitHub credentials in Git](https://docs.github.com/en/github/getting-started-with-github/caching-your-github-credentials-in-git)."


# Application required commands <a name="applicationCommands"></a>

## Clone repository

> $ git clone https://github.com/opsup/SAM.git

## Set git config

> $ git config --global user.email support@outpostsentinel.com
>
> $ git config --global user.name support 

## Check active branch

> $ git branch -a
> 
> \* master
> 
>   remotes/origin/HEAD -> origin/master
> 
>   remotes/origin/master
> 
>   remotes/origin/original-code
> 
>   remotes/origin/updated-code

## Switch branch

> $git checkout updated-code 
> 
> Branch 'updated-code' set up to track remote branch 'updated-code' from 'origin'.
> 
> Switched to a new branch 'updated-code'

## Check files status

> $ git status
> 
> On branch updated-code
> 
> Your branch is up to date with 'origin/updated-code'.
> 
> nothing to commit, working tree clean

## Show all adding or modify files and directories

> $ git status

`List of files and folders will appear in 'Red' as not added.`

## To add all items

$ git add .

`Show all adding or modify files and directories`

> $ git status

`List of files and folders will appear in 'Green' as now added.`

## Adding a commit with message

> $ git commit -m "Commit message in quotes"

## Show entire git log (optional)

> $ git log

## Push a specific branch to a remote with named remote

> $ git push origin updated-code
> 
> Username for 'https://github.com': opsup
> 
> Password for 'https://opsup@github.com': 
> 
> :
> 
> :

## Pull from named remote

> $ git pull origin updated-code 
> 
> Username for 'https://github.com': opsup
> 
> Password for 'https://opsup@github.com': 
> 
> From https://github.com/opsup/SAM
> 
>  \* branch            updated-code -> FETCH_HEAD
> 
> :
> 
> :       

# Detailed Explaination on some of the basic needed git commands <a name="explaination"></a>

## Change directory to codebase

> $ cd /file/path/to/code

## Clone the repository

> $ git clone <remote_URL>

> $ git clone https://github.com/opsup/SAM.git
> 
> Cloning into 'SAM'...
> 
> Username for 'https://github.com': <username>
> 
> Password for 'https://opsup@github.com': <password>

## Running git config globally

> $ git config --global user.email <email>
> 
> $ git config --global user.name <name>

## Running git config on the current repository settings

> $ git config user.email <email>
> 
> $ git config user.name <name>
> 
  
## Verify git config settings

> $ git config user.email
> 
> $ git config user.name

## Git Branch

  #### Create a new branch

> $ git branch <branch_name>

  #### List all remote or local branches

> $ git branch -a

  #### Delete a branch

> $ git branch -d <branch_name>

## Git Checkout

  #### Checkout an existing branch

> $ git checkout <branch_name>

  #### Checkout and create a new branch with that name

> $ git checkout -b <new_branch>

## Git Status

`Git status returns the current state of the repository.`
  
`Modified files will appear in 'red' if not added, else will be in 'green' if added to current branch.`

> $ git status

## Git Add

  #### Adds files in the to the staging area for Git.

> $ git add <file or directory name>

  #### To add all files not staged:

> $ git add .

#### To stage a specific file:

> $ git add xxxx.html

#### To stage an entire directory:

> $ git add <directory>

# Adding a commit with message

> $ git commit -m "Commit message in quotes"

## Git Push

  #### Git push sends local commits to the remote repository.

> $ git push <remote_URL/remote_name> <branch>

  #### Push all local branches to remote repository

> $ git push —all

## git pull to get the latest version of a repository run git pull.

> $ git pull <branch_name> <remote_URL/remote_name>

## Git Log

  #### Show entire git log

> $ git log

  #### Show git log with date pameters

> $ git log --<after/before/since/until>=<date>

  #### Show git log based on commit author

> $ git log --<author>="Author Name"
