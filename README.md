# versionControl-git
Record for git commands
# versionControl-git
Record for git commands

git init                                                  # Initialize local git repository (create new repository)
git config --global user.name "xxx"                       # Config username -- globally 
git config --global user.email "xxx@xxx.com"              # Config email -- globally
git config --global color.ui true                         # git status, etc auto fill color
git config --global color.status auto
git config --global color.diff auto
git config --global color.branch auto
git config --global color.interactive auto
git config --global --unset http.proxy                    # remove  proxy configuration on git
git clone git+ssh://git@192.168.xx.xxx/VT.git             # clone repo
git status                                                # View the current version status (modified or not)
git add xyz                                               # Add xyz file to index
git add .                                                 # Add all changed files in the current subdirectory to index
git commit -m 'xxx'                                       # submit
git commit --amend -m 'xxx'                               # Merge the last commit (for repeated revisions)
git commit -am 'xxx'                                      # Combine add and commit into one step
git rm xxx                                                # delete files in index
git rm -r *                                               # delete recursively
git log                                                   # show log
git log -1                                                # Display 1 line of log -n is n lines
git log -5
git log --stat                                            # Display the commit log and related change files
git log -p -m
git show dfb02e6e4f2f7b573337763e5c0013802e392818         # Show details of a commit
git show dfb02                                            # Use the first few digits of the commitid 
git show HEAD                                             # Show HEAD commit log
git show HEAD^                                            # Displays the commit log of the parent (previous revision) of HEAD ^^ is the last two revisions ^5 is the last                                                           # 5 revisions
git tag                                                   # Show existing tag
git tag -a v2.0 -m 'xxx'                                  # Add the tag of v2.0
git show v2.0                                             # Display logs and details of v2.0
git log v2.0                                              # Display logs for v2.0
git diff                                                  # Display all changes not added to index
git diff --cached                                         # Display all changes that have been indexed but not yet committed
git diff HEAD^                                            # Compare the differences from the previous version
git diff HEAD -- ./lib                                    # Compare differences with HEAD version lib directory
git diff origin/master..master                            # Compare the remote branch master with the local branch master without
git diff origin/master..master --stat                     # Only display the difference files, not the specific content
git remote add origin git+ssh://git@192.168.XX.XXX/VT.git # Add remote definition (for push/pull/fetch)

git branch                                                # Display local branches
git branch --contains 50089                               # Display the branch containing commit 50089
git branch -a                                             # Display all branches
git branch -r                                             # Display all original branches
git branch --merged                                       # Display all branches that have been merged into the current branch
git branch --no-merged                                    # Display all branches not merged into the current branch
git branch -m master master_copy                          # Rename branch 
git checkout -b master_copy                               # Create new branch master_copy from current branch and checkout
git checkout -b master master_copy                        # Contain all above ⬆️⬆️⬆️

git checkout features/performance                         # Check out the existing features/performance branch
git checkout --track hotfixes/BJVEP933                    # Checkout the remote branch hotfixes/BJVEP933 and create a local tracking branch
git checkout v2.0                                         # Checkout version v2.0
git checkout -b devel origin/develop                      # Create new local branch develop from remote branch develop and checkout
git checkout -- README                                    # Check out the README file for the head version (can be used to modify error fallbacks)
git merge origin/master                                   # Merge the remote master branch to the current branch
git cherry-pick ff44785404a8e                             # Merge changes from commit ff44785404a8e
git push origin master                                    # Push the current branch to the remote master branch
git push origin :hotfixes/BJVEP933                        # Delete the hotfixes/BJVEP933 branch of the remote repository
git push --tags                                           # Push all tags to the remote repository
git fetch                                                 # Get all remote branches (do not update local branches, and merge）
git fetch --prune                                         # Get all original branches and clear deleted branches on the server
git pull origin master                                    # Get the remote branch master and merge to the current branch
git mv README README2                                     # Rename the file README to README2
git reset --hard HEAD                                     # Reset the current version to HEAD (usually used for merge failure fallback)
git rebase
git branch -d hotfixes/BJVEP933                           # Delete branch hotfixes/BJVEP933 (modifications of this branch have been merged into other branches)
git branch -D hotfixes/BJVEP933                           # Force delete branch hotfixes/BJVEP933
git ls-files                                              # List files included in git index
git show-branch                                           # Graphical current branch history
git show-branch --all                                     # Graphical history of all branches
git whatchanged                                           # Display file modifications corresponding to the commit history
git revert xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx       # undo commit xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
git ls-tree HEAD                                          # Internal command: display a git object
git rev-parse v2.0                                        # Internal command: display the SHA1 HASH of a ref for
git reflog                                                # Show all commits, including orphaned nodes
git show HEAD@{5}
git show master@{yesterday}                               # Show the status of the master branch yesterday
git log --pretty=format:'%h %s' --graph                   # Graphical commit log
git show HEAD~3
git show -s --pretty=raw 2be7fcb476
git stash                                                 # Temporarily save the current changes and set all to HEAD state
git stash list                                            # View all staging
git stash show -p stash@{0}                               # Refer to the first staging
git stash apply stash@{0}                                 # The first time the application is staged
git grep "delete from"                                    # Search for the text "delete from" in the file

