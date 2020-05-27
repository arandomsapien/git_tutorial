# Command Log

Here are all the commands I've used so far:

> git init
: This command created the repo

> git add README.txt
: Added the README.txt file to the staging area

> git commit -m "Initial commit"
: Did an initial commit with that README.txt file

hmm... I should probably add define some terms. What is a staging area?

Time to BRANCH OUT and start a new feature! ahahahaha...

> git checkout -b git_terminology
: This command created a new branch where I'll create a git_terminology.md file

I created a file with some basic terminology and added it.

> git add git_terminology.md

Time to get it committed. 

> git commit -m "Added terminology file"

I should probably add a line about this change to the README so people will know what's in that file.

Since README.txt is already tracked, I can use `git commit -am` and a message to add all changes to tracked files to the current commit.

> git commit -am "Updating README.txt with git_terminology.md"

I made a mistake and need to undo the last commit!

> git reset --soft HEAD~1
: This will undo the commit but preserve the changes I made so I can patch it up. No one will be the wiser. EVIL LAUGH.

Time to commit this change again and switch back to the master branch for some more work there. 

> git commit -am "Updating README.txt with git_terminology.md"
: Same command as last time, but I fixed my mistake!

> git checkout master

Here I am safely back on the master branch. 

I just realized, my command_log.md file isn't staged! Time to remedy that.

> git add command_log.md

While I'm here, I think I should add a KEY FILES section to the README to join that mention in the other branch. 

Since both these files are already tracked, I'll run `git commit` with the `-am` switches

> git commit -am "Added key files section to the readme"

I think that other branch is all done being developed. Time to merge it back in.

> git merge git_terminology

AN ERROR?! Say it ain't so.

```
Auto-merging README.txt
CONFLICT (content): Merge conflict in README.txt
Automatic merge failed; fix conflicts and then commit the result.
```

How can I fix this... 

Since I'm in Visual Studio Code, I went to the git plugin and see a 'C' beside the README.txt file... That might mean there's a conflict to solve!

Clicking on the file actually shows the diff. I want to keep both changes though, so I'll click that option.

Now that I've fixed the conflict, I'll create a commit with that un-broken file.

> git commit -am "fixing merge conflicts"

What does the log say now?

> git log --oneline

```
db50789 (HEAD -> master) fixing merge conflicts
1f37354 Added key files section to the readme
072783b Added command_log.md file
662f04c (git_terminology) Updating README.txt with git_terminology.md
24141f2 Added terminology file
73a2238 Initial commit
```

Perfect. Time to commit this last change to the command_log.md file and be done with it, for now. 