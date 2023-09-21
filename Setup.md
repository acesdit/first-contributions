# Setting up Git to work with your GitHub account

Download & Install Git for your operating system from [https://git-scm.com/downloads](https://git-scm.com/downloads)

## Add your username & email to git config

Execute the following commands with your github account credentials to let git know your username & email

```bash
git config --global user.name <YOUR_USERNAME>
git config --global user.email <YOUR_EMAIL>
```

## Set up SSH

Follow the instructions for your operating system.

<!-- WINDOWS -->
<details>
<summary>For Windows</summary>

### Generating a new SSH key

1. Open Git Bash
2. Paste below text, with your GitHub email address, for generating a SSH key

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

3. Accept default choices by pressing enter on prompts
4. You've successfully created your SSH key, next add your key to ssh-agent

### Adding SSH key to ssh-agent

1. Ensure ssh-agent is running by running first line of below text

```bash
eval "$(ssh-agent -s)"
```
> Agent pid 59566


If you see a similar output, proceed to next step

2. Add your SSH private key to ssh-agent

```bash
ssh-add ~/.ssh/id_ed25519
```

### Adding SSH key to your GitHub account

1. Copy public key to your clipboard

```bash
clip < ~/.ssh/id_ed25519.pub
```

2. Go to GitHub website and click on your profile photo, then click **Settings**
3. In the "Access" section of the sidebar, click **SSH and GPG keys**
4. Click **New SSH key** or **Add SSH key**
5. In the "Title" field, add a name of your choice for your computer.
6. In the "Key field", paste your public key.
7. Click **Add SSH key**
8. If prompted, confirm access to GitHub account

### Testing your SSH connection

1. Execute the following code in git bash

```bash
ssh -T git@github.com
```

2. If a warning pops up, type yes
3. You should see a message similar to this, with your username

```
> Hi USERNAME! You've successfully authenticated, but GitHub does not provide shell access
```

</details>

<!-- MACOS -->
<details>
<summary>For MacOS</summary>

### Generating a new SSH key

1. Open Terminal
2. Paste below text, with your GitHub email address, for generating a SSH key

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

3. Accept default choices by pressing enter on prompts
4. You've successfully created your SSH key, next add your key to ssh-agent

### Adding SSH key to ssh-agent

1. Ensure ssh-agent is running by running first line of below text

```bash
eval "$(ssh-agent -s)"

```
> Agent pid 59566

If you see a similar output, proceed to next step

2. If using MacOS Sierra 10.12.2 or later, you will need to modify your `~/.ssh/config` file to automatically load keys into the ssh-agent and store passphrases in your keychain.

- First, check if file already exists in the default location

```bash
open ~/.ssh/config
```

- If file doesn't exist, create the file

```bash
touch ~/.ssh/config
```

- Open the file and modify it to contain the following lines.

```
Host github.com
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/id_ed25519
```

2. Add your SSH private key to ssh-agent

```bash
ssh-add --apple-use-keychain ~/.ssh/id_ed25519
```

### Adding SSH key to your GitHub account

1. Copy public key to your clipboard

```bash
pbcopy < ~/.ssh/id_ed25519.pub
```

2. Go to GitHub website and click on your profile photo, then click **Settings**
3. In the "Access" section of the sidebar, click **SSH and GPG keys**
4. Click **New SSH key** or **Add SSH key**
5. In the "Title" field, add a name of your choice for your computer.
6. In the "Key field", paste your public key.
7. Click **Add SSH key**
8. If prompted, confirm access to GitHub account

### Testing your SSH connection

1. Execute the following code in terminal

```bash
ssh -T git@github.com
```

2. If a warning pops up, type yes
3. You should see a message similar to this, with your username

```
> Hi USERNAME! You've successfully authenticated, but GitHub does not provide shell access
```

</details>

<!-- LINUS -->
<details>
<summary>For Linux</summary>

### Generating a new SSH key

1. Open Terminal
2. Paste below text, with your GitHub email address, for generating a SSH key

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

3. Accept default choices by pressing enter on prompts
4. You've successfully created your SSH key, next add your key to ssh-agent

### Adding SSH key to ssh-agent

1. Ensure ssh-agent is running by running first line of below text

```bash
eval "$(ssh-agent -s)"
```
> Agent pid 59566

If you see a similar output, proceed to next step

2. Add your SSH private key to ssh-agent

```bash
ssh-add ~/.ssh/id_ed25519
```

### Adding SSH key to your GitHub account

1. Copy public key to your clipboard

```bash
cat ~/.ssh/id_ed25519.pub
# Select & copy the contents of the id_ed25519.pub file
# displayed in the terminal to your clipboard
```

2. Go to GitHub website and click on your profile photo, then click **Settings**
3. In the "Access" section of the sidebar, click **SSH and GPG keys**
4. Click **New SSH key** or **Add SSH key**
5. In the "Title" field, add a name of your choice for your computer.
6. In the "Key field", paste your public key.
7. Click **Add SSH key**
8. If prompted, confirm access to GitHub account

### Testing your SSH connection

1. Execute the following code in terminal

```bash
ssh -T git@github.com
```

2. If a warning pops up, type yes
3. You should see a message similar to this, with your username

```
> Hi USERNAME! You've successfully authenticated, but GitHub does not provide shell access
```

</details>
