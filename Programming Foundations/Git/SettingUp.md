# Git Setting Up

We use git for our version system management and for cloning projects we have two ways in gitlab either you can use `ssh` or `https`

## Clone Project via

### 1. **SSH**

<!-- Coming Soon -->

### 2. **HTTPS**

#### **Discovering HTTPS:**

Let’s start by explaining what the famous HTTPS means, we’ll need it later. In short, it is the encrypted version of HTTP, period. But then what is HTTP? It is a protocol that works in client-server communication, thanks to which the Internet exists as we know it. HTTP supports different types of requests, depending on what we want to send, e.g. a specific resource or a completed form. What distinguishes these two protocols is the letter S, meaning Secure. Despite such a small difference in name, the difference in operation is huge because HTTPS is an encrypted connection! The TLS protocol is responsible for it, which first performs key exchange to verify the security of the connection, and only then the HTTP request is made.

To clone a repository we just need to type such command: 

```shell
git clone <REPOSITORY_ADDRESS>
```

For example for cloning this repo you should run this command:

```shell
git clone https://github.com/notionwave/roadmap.git
```

the problem or downside of using HTTPS to clone project and work with git is you can't save your credentials and for any action that you will do with remote you have to pass authorization and it is annoying in order to avoid this you can use  [git-credential-manager](https://github.com/GitCredentialManager/git-credential-manager). it will store your credential with encrypting it into a gpg file in your file system so after you configured it will automatically pass authorization, So let's configure it.

#### **How to install & use Git-Credential-Manager:**

**Linux**:

  1. Download the latest .deb package from [here](https://github.com/GitCredentialManager/git-credential-manager/releases/tag/v2.0.785)

  2. Run below commands in your terminal and follow prompts:

  ```shell
  sudo dpkg -i <path-to-package>
  
  git-credential-manager-core configure

  git config --global credential.credentialStore gpg

  gpg --gen-key 

  sudo apt install pass

  pass init <gpg-id> # gpg-id is the uid
  ```

After you run all above command you will talk with git remote without passing credentials each time and git-credential manager will automatically authorize you. 