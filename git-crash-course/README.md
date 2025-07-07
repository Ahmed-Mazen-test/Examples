## git Hidden folder

There is a hidden folder called `.git` which tells you that your project is a git repo.

if we wanted to create a git repo in a new project we initilize it using `git init`

```sh
mkdir /workspaces/tmp/new-project
cd /workspaces/tmp/new-project
git init
touch README.md
code README.md
git status
git add .
# make changes to README.md
git commit -m "add readme file"
```

## Cloning

we can clone three ways: HTTPS, SSH, Github CLI

Since we are using github codespaces we'll create a temprary directory in our workspace

~~~sh
mkdir /workspace/tmp
cd /workspace/tmp
~~~


### HTTPS

~~~sh
git clone https://github.com/Ahmed-Mazen-test/Examples.git
cd Examples
~~~
> you'll need to generate a github personal access token [PAT](https://github.com/settings/personal-access-tokens)

you'll use you PAT as your password when you login 

- give it access for commits

### ssh

```sh
git clone git@github.com:Ahmed-Mazen-test/Examples.git
cd Examples
```

We will need to create our own ssh key pair

```sh
ssh-keygen -t rsa
```

for WSL users and if you create a non default key you might need to add it

```sh
eval 'ssh-agent'
ssh-add /home/user/.ssh/[key]
```

We can test our connection here
```sh
ssh -T git@github.com
``` 

### Github CLI

install thr CLI

eg. Linux (Ubuntu)
```sh 
(type -p wget >/dev/null || (sudo apt update && sudo apt install wget -y)) \
	&& sudo mkdir -p -m 755 /etc/apt/keyrings \
	&& out=$(mktemp) && wget -nv -O$out https://cli.github.com/packages/githubcli-archive-keyring.gpg \
	&& cat $out | sudo tee /etc/apt/keyrings/githubcli-archive-keyring.gpg > /dev/null \
	&& sudo chmod go+r /etc/apt/keyrings/githubcli-archive-keyring.gpg \
	&& sudo mkdir -p -m 755 /etc/apt/sources.list.d \
	&& echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null \
	&& sudo apt update \
	&& sudo apt install gh -y
```

## Comits
when we want to commit code we can write git commit which will open up the commit edit message in you editor of choice

```sh
git commit
```

set the global editor

```sh
git config --global core.editor nvim
```

make a commit and commit message without opening an editor.

```sh
git commit -m "add two !"
```

## Branches

## Remotes

## Stashing

## Merging

## add

when we want to stage changes that will be included in the commit we can use the `.` to add all possible file.

```sh
git add README.md
git add .
```

## Reset

Reset allows you to move staged changes to be unstaged. this is useful when you want to change all the files to be not commited
```sh
git add .
git reset
```
> git reset will revert a git add .

## status

it shows you what files will and will not be commited

```sh
git status
```

## gitconfig file

the gitconfig file is what stores your global configurations for git such as emal, name, editor and more.

showing the content of our `.gitconfig` file

```sh
git config --list
```

when you first install git on a machine you are supposed to set up your name and email

```sh
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
```

## log

git log will show recent git commits to the git tree

```sh
git log
```

## push

when we want to push a repo to our remote orgin 

```sh
git push 
```