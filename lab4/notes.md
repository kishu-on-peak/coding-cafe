# Lab 4 Notes

## Question 1
`--global` means the setting applies to my whole user account, so every repo on this laptop uses the same name and email. If I left it out, Git would only set it for the current repo (in its `.git/config`), and I'd have to repeat it in every new project.

## Question 2
`.git` appeared in `ls -a` but not in `ls`, because it's a hidden folder. It holds the whole repository: the commit history, config, branches, and the stored versions of my files.

## Question 3
Git offered to track about 4 things: `.DS_Store`, `README.md`, `week01/` and `week02/`. The `.DS_Store` file is something I didn't write, since macOS creates it automatically.

## Question 4
`.DS_Store` disappeared from the list because `.gitignore` now tells Git to ignore it. `.gitignore` itself appeared as a new untracked file.

## Question 5
It should be committed, not ignored. It's a real project file, and committing it means anyone who clones the repo gets the same ignore rules.

## Question 6
`README.md` moved from "Untracked files" to "Changes to be committed". In the three-places model, it moved from the working directory to the staging area.

## Question 7
Git printed `[main (root-commit) 4feff81] Lab work so far`, then said 5 files changed with 1309 insertions. (I later amended the commit to fix my email, so the hash is now `32bb65a`.)

## Question 8
The first seven characters (`32bb65a`) are the short commit hash. It's a unique ID for that commit, so I can refer to it without typing the full 40 characters.
