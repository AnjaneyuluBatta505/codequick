# Git Quick Reference

* Git Configuration
  ```bash
  $ git config --global user.name "Anjaneyulu Batta"
  $ git config --global user.email anjaneyulu.batta505@gmail.com
  ```
 
* Git Code Editor

  ```bash
  $ git config --global core.editor vim
  ```

* Git `commit.template`

  For instance, consider a template file at `~/.gitmessage.txt` that looks like this:

  ```txt
  Subject line (try to keep under 50 characters)

  Multi-line description of commit,
  feel free to be detailed.

  [Ticket: X]
  ```
  Now, set the template
  ```bash
  $ git config --global commit.template ~/.gitmessage.txt
  $ git commit
  ```

* Revert last merge/pull on a branch
  ```bash
  git merge --abort
  ```
* Revert last commit
  ```
  git reset --hard HEAD~1
  ```
