# Contributing to OpenDevStack

The following is a set of guidelines for contributing to [OpenDevStack](https://github.com/opendevstack) and its related packages and tools.  

#### Table Of Contents

[How to setup](#how-to-setup)

[How to update](#how-to-update)

[How to contribute](#how-to-contribute)


## How to setup
* Fork all relevant repositories into your GitHub account.
* Clone the repositories from either your fork or the OpenDevStack GitHub repository.
* Add the github/opendevstack master as a remote called '*github-opendevstack*' and also your fork as '*github-<YOUR_GITHUB_ACCOUNT_NAME>*'
  ```sh
  git remote add github-opendevstack https://github.com/opendevstack/<REPO_NAME>.git
  git remote add github-<YOUR_GITHUB_ACCOUNT_NAME> https://github.com/<YOUR_GITHUB_ACCOUNT_NAME>/<REPO_NAME>.git
  ```
* On how to initially install and get started with OpenDevStack, please refer to the [Getting Started](https://github.com/opendevstack) guide.
* Once it is installed and the Bitbucket server is running, create the equivalent repositories manually on your Bitbucket server.
* Add these newly created repos as a remote with the name '*bitbucket-opendevstack*' to your local repos.
  ```sh
  git remote add bitbucket-opendevstack <YOUR_BITBUCKET_REPO_URL>
  ```
* Push the corresponding code into this new '*bitbucket-opendevstack*' remote repo.
  ```sh
  git push -u bitbucket-opendevstack master
  ```
* Create an *ods-configuration* repo that contains all property values (e.g. Nexus URL) on Bitbucket. See the *ods-configuration-sample* example repo on GitHub for more information.


## How to update
* Checkout master.

* Fetch updates from '*github-opendevstack*' remote.

* Merge '*github-opendevstack/master*' or a certain tag into your local master.

* Push the merged changes from your local master to '*github-<YOUR_GITHUB_ACCOUNT_NAME>/master*' remote. (Optional)

* Push the merged changes from your local master to '*bitbucket-opendevstack/master*' remote.

* Create a Pull Request on Bitbucket master to production branch for the changes we pushed to master in the previous step.

* Check the changelog for anything to update/reinstall via change-scripts, new ods-configuration properties etc. and do it.


**Git Example:**
```sh
  git checkout master
  git fetch github-opendevstack
  git merge github-opendevstack/1.1
  git push master github-<YOUR_GITHUB_ACCOUNT_NAME>/master
  git push master bitbucket-opendevstack/master
  # -> Create PR on Bitbucket *master* to *production*
```
  
  

## How to contribute
* Create a branch.
  ```sh
  git checkout -b <BRANCH_NAME>
  ```

* Make your code changes in this branch.

* After finishing, push this branch to bitbucket-opendevstack
  ```sh
  git push bitbucket-opendevstack <BRANCH_NAME>
  ```
  
* Create a PR to the Bitbucket production branch and wait until it gets approved and merge it.

* Push your branch to your forked repo on GitHub.
  ```sh
  git push github-<YOUR_GITHUB_ACCOUNT_NAME> <BRANCH_NAME>
  ```

* Create a PR from this branch on your GitHub repo to the OpenDevStack GitHub repo. 


**Git Example:**
```sh
  git checkout -b fix/typo
  git push bitbucket-opendevstack fix/typo
  # -> Create PR on Bitbucket based on *fix/typo* got approved  
  git push github-<your_github_account_name> fix/typo 
  # -> Create PR *github-<your_github_account_name>/fix/typo* to *github-opendevstack/master*
```
