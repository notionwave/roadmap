# Git Setting Up

We use git for our version system management and for cloning projects we have two ways in gitlab either you can use `ssh` or `https`

## Clone Project via

### 1. **SSH**

<!-- Coming Soon -->

### 2. **HTTPS**

To clone a repository we just need to type such command: 

```shell
git clone <REPOSITORY_ADDRESS>
```

For example for cloning this repo you should run this command:

```shell
git clone https://github.com/notionwave/roadmap.git
```

the problem or downside of using HTTPS to clone project and work with git is you can't save your credentials and for any action that you will do with remote you have to pass authorization and it is annoying in order to avoid this you can use  [git-credential-manager](https://github.com/GitCredentialManager/git-credential-manager). it will store your credential with encrypting it into a gpg file in your file system so after you configured it will automatically pass authorization, So let's configure it.

#### **Git-Credential-Manager:**

By installing git credential manager you won't need to enter passwords every time.
Follow its [installation guidelines](https://github.com/git-ecosystem/git-credential-manager/blob/release/docs/install.md) for your OS.
