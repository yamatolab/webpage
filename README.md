# Yamato Lab Webpage

## How to develop

### Setup

Clone repository

```shell
# HTTPS
git clone https://github.com/yamatolab/webpage.git

# or SSH
git clone git@github.com:yamatolab/webpage.git
```

Check that working branch is `develop`. 

```shell
$ git branch
```

If not, Please checkout to `develop` branch.

```shell
git pull origin develop
git checkout develop
```

Now, we have got files. Next, we'll prepare develop environment.

Please check your python version is upper than 3.x

We'll install `sphinx-build` and `sphinx-autobuild`

- `sphinx-build` is builder of sphinx. Production page and Test page are generated by this.
- `sphinx-autobuild` is Live viewing tool for develop.

You can use `pip`

```shell
pip install sphinx-build sphinx-autobuild
```

Check if installation is successful.

```shell
cd webpage
sphinx-autobuild -c . pages public/yamato-lab
```

Can you see output like below ? Access http://localhost:8000/ .

```shell
[I 210903 14:04:15 server:335] Serving on http://127.0.0.1:8000
[I 210903 14:04:15 handlers:62] Start watching changes
[I 210903 14:04:15 handlers:64] Start detecting changes
```

If you can visit familiar page, Your installation is successful!

### Start develop

To check your changes on live, run below command.

```shell
sphinx-autobuild -c . pages public/yamato-lab
```

Create new branch to develop new feature or write document, etc.

And then, Checkout the new branch.

```shell
# Check your branch is develop.
git branch

# Create new branch and checkout.
# this command is the same as git branch feature/update_research && git checkout feature/update_research
git checkout -b feature/update_research

# You can also use this command for creating branch from develop branch explicity.
# This command is the same as git checkout develop && git checkout -b feature/update_research
git checkout -b feature/update_research develop
```

Write your code and check via browser http://localhost:8000/

When your work has done, create commit(s) and push it.

```shell
# Create commit(s).
git add /path/to/changed/file
git commit -m "Add new papers to research page"

# To avoid conflict on remote branch, check on local.
# No Fatal error is OK. Please resolve conflict on local.
git pull origin develop
git merge develop

# Push your commit(s)!
git push origin feature/update_research
```

### Reflect your commit.

Open https://github.com/yamatolab/webpage and create pull request to develop branch.

- [Creating a pull request](https://docs.github.com/en/github/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request)
- [プルリクエストの作成方法](https://docs.github.com/ja/github/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request)

Mergin Pull request is only allowed by two member's approval.