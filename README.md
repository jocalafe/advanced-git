# Advanced Git Workflows

## It all starts with the messages

We’ve all used commit messages like `fix`, `fix: PR comments`, `test commit`. These types of messages do not give any context to the changes the commit is introducing and only clutter the history. Instead of explaining why that commit exists, all messages should explain the changes it contains. 

As a general rule, all pushed commit messages should follow these guidelines:

- Only contain changes to a delimited area of the code base.
- Have a short and clear description of the change.
- Use the imperative, present tense: "change" not "changed" nor "changes".
- Don't capitalize the first letter.
- No dot (.) at the end.

With the help of Conventional Commits `types`, we can more accurately describe our changes:

- **build**: Changes that affect the build system or external dependencies (example scopes: Webpack, Babel, Typescript, npm)
- **ci**: Changes to our CI configuration files and scripts (example scopes: Github Workflows, Dockerfiles)
- **docs**: Documentation only changes
- **feat**: A new feature
- **fix**: A bug fix
- **perf**: A code change that improves performance
- **refactor**: A code change that neither fixes a bug nor adds a feature
- **style**: Changes that do not affect the meaning of the code (white space, formatting, missing semi-colons, etc) **NOT CSS CHANGES**
- **test**: Adding missing tests or correcting existing tests
- **chore:**  Other changes that don't modify `src` or `test` files

## Scope down PRs

When collaborating with multiple people and working with multiple interdependent PRs it is really important to keep a clean history. In addition to a clean history, well-scoped commits will help you write more concise messages, and will reduce the number of conflicts that you will need to resolve.

PRs should be small so they are easy to review, test and iterate. Most of the time you will need to break up a single task into multiple PRs. This will require some extra work but will also ensure that your reviewers can clearly see the intent of the PR allowing them to make an efficient and easy review.
We also believe that creating small PRs leads to better code since each part of will be independent and less coupled to the rest.

As a bonus benefit, small PRs can even help you reduce the downtime you have while waiting for someone to review a PR for you. Not only will the review time be shorter for a small PR, but since your work is divided into multiple independent parts you will be able to work on a different piece of the task while your initial PR is being reviewed.

Before starting to code it is really helpful to take a moment to think about the different parts you will need to work on to complete a task and define how many PRs and commits you think will be necessary.

- Will I need to make API requests?
- How many components will I need to create?
- Do I need to change any existing code?
- Are my changes breaking changes?

The answer to these and many other questions will help you better understand the changes you will need to make and help you break them down into individual, well-scoped commits and PRs.

It might feel daunting at first but I can assure you that after some practice it will become second nature.

💡 Uh oh, my previous commit message/files no longer make any sense. What can I do?
[Rebase Interactive](./rebase-interactive.md) to the rescue!


💡 My PR has turned into a huge monster 👹, how can I fix this?
Take a look at the [Cherry-Pick](./cherry-pick.md) command!


## How to handle a rebase on the base branch?

Base branches should be rebased seldomly and only when it is unavoidable.

🚫 You should never rebase a remote base branch without the approval of everyone that is using that branch.


When working with multiple branches for long periods of time it is common that you may need to rebase the base branch. Rebase rewrites history, which means that some existing commits might change their SHAs, and git will be unable to match the same commit when rebasing.

💡 [Rebase Interactive](./rebase-interactive.md) with its drop command can help us remove the duplicated commits.

## Reflog

It makes sense if all of these new commands make you uneasy, we’ve all felt like crying after accidentally deleting a bunch of code we had worked on for hours.

Sweat no more, [Reflog](./reflog.md) is here to the rescue!

## Resources:

[https://github.com/jocalafe/advanced-git](https://github.com/jocalafe/advanced-git)

[Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)

[Advanced Git Tutorial - Interactive Rebase, Cherry-Picking, Reflog, Submodules and more](https://www.youtube.com/watch?v=qsTthZi23VE)

[How to Scope Down PRs](https://www.netlify.com/blog/2020/03/31/how-to-scope-down-prs/)
