wc -l ~/coding-cafe/week02/lab01-log.txt
# Coding Café - Lab 1 Notes

1. `pwd` printed my home directory path, /Users/boorakinshuk.

2. `ls -a` showed hidden files/folders (ones starting with a dot, like .zshrc
   and .vscode), which plain `ls` doesn't display since it hides dotfiles
   by default.

3. The first column of `ls -l` (e.g. drwx------@) shows the file type and
   permissions. The first character tells you the type: `d` means directory,
   `-` means a regular file. The rest describes read/write/execute
   permissions for the owner, group, and others.

4. `coding-cafe/week02` is a relative path - it depends on where I'm
   standing. It worked because I was in /Users/boorakinshuk, which contains
   a coding-cafe folder. An absolute path starts with `/` and works from
   anywhere, e.g. /Users/boorakinshuk/coding-cafe/week02.

5. `mv` did two different jobs: first it moved a file into a different
   folder (week01/), then it renamed a file in place (README-backup.md to
   old-readme.md). Both are really the same operation - "moving" a file to
   a new path - renaming is just moving to a new name in the same location.

6. My PATH has multiple folders separated by colons. I counted them using
   `echo $PATH | tr ':' '\n' | wc -l`.

7. My python3 lives at:
   /Library/Frameworks/Python.framework/Versions/3.14/bin/python3

8. My python3 path is specific to how I installed Python (via the official
   python.org installer, which puts it under /Library/Frameworks). Someone
   using Homebrew or the system default would get a different path -
   different install methods put Python in different locations.

9. The shell said `zsh: command not found: pyton3`. This means the shell
   searched every folder listed in my PATH and didn't find any program
   called "pyton3" - because of the typo, it's looking for a program that
   simply doesn't exist. Python itself isn't broken; this exact name just
   isn't on the PATH.

10. `.venv` didn't show up with plain `ls` because it's a hidden folder -
    its name starts with a dot, and `ls` hides dotfiles by default. `ls -a`
    shows all files, including hidden ones.

11. `(.venv)` appeared at the very start of my prompt, showing I'm now
    "inside" the virtual environment.

12. Yes, `which python3` gave a different path after activating:
    /Users/boorakinshuk/coding-cafe/.venv/bin/python3, instead of the
    system one. This shows that `activate` doesn't install a new Python -
    it edits my PATH to put .venv/bin at the very front, so the shell finds
    that folder's python3 before any other.

13. The second `pip list` had `requests` plus four extra packages: certifi,
    charset-normalizer, idna, and urllib3. These are dependencies that
    `requests` needs to work, so pip automatically installed them too when
    I asked for just one package.

14. After `deactivate`, `python3` pointed back to the system-wide install:
    /Library/Frameworks/Python.framework/Versions/3.14/bin/python3 - exactly
    where it was before I activated the venv. `deactivate` removes .venv/bin
    from the front of PATH, restoring the normal PATH.

15. `ls -h` makes file sizes "human-readable" when combined with `-l`.
    Instead of showing raw byte counts (like 2880), it shows sizes with
    unit suffixes like K, M, G, etc., so they're easier to read at a glance.

16. Ctrl+C interrupts/cancels whatever is currently running but keeps the
    program open - I stayed inside Python and just got a new >>> prompt
    with a "KeyboardInterrupt" message. Ctrl+D signals "end of input" and
    closes the program entirely, sending me back to the normal shell prompt.
