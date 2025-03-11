# nikol-website-on-github

## Website repositories on github.com/irsbugs 

Note: 2 factor authenticator using mobile phone 2025-03-11

You have enabled two-factor authentication using SMS.

=====

irsbugs.github.io <--- Ian simple website 

hampug-connect <-- Demonstration of websockets Four-in-a-row game

my-website <-- Demo web site for Te Whare O Te Ata

nikola-website-on-github <-- Information on Moving a nikola website: To be cleaned up

=====

## Other websites:

hampug.github.io <--- Now on HamPUG github repository

Web sites for JD:
jd_simple_website.github.io
jd_complex_folders_website.github.io


Website template for Te Papanui Enderley Community Tust
papanui.github.io

=====



## Moving a nikola website on a PC to a Github account web site.

On a Linux PC do the following to create a Nikola website:

* Use the Nikola Getting Started https://getnikola.com/getting-started.html 

* First, make sure Python 3 is installed.
On Debian/Ubuntu, you also need the python3-venv package.

When you are done installing, run:
$ python3 -m venv nikola-env
$ cd nikola-env
$ bin/python -m pip install -U pip setuptools wheel
$ bin/python -m pip install -U "Nikola[extras]"
...snip...
Successfully installed Nikola

You can now use Nikola by launching the script directly:
$ bin/nikola

Or you can activate the environment before working
with Nikola and use the nikola command:
$ source bin/activate
$ nikola

Creating a Site (Not a Blog) with Nikola
https://getnikola.com/creating-a-site-not-a-blog-with-nikola.html

Create an empty repository on Github
github-account-name.gihub.io



# github_deploy configuration
# For more details, read the manual:
# https://getnikola.com/handbook.html#deploying-to-github
# You will need to configure the deployment branch on GitHub.
GITHUB_SOURCE_BRANCH = 'src'
GITHUB_DEPLOY_BRANCH = 'main' # Was 'master' Ian 2025-03-03

# The name of the remote where you wish to push to, using github_deploy.
GITHUB_REMOTE_NAME = 'origin'

# Whether or not github_deploy should commit to the source branch automatically
# before deploying.
GITHUB_COMMIT_SOURCE = True


---

# Moving the website

ian@hp:~$ cd hampug-merged-website/


ian@hp:~/hampug-merged-website$ cd hampug.github.io/
ian@hp:~/hampug-merged-website/hampug.github.io$ 
ian@hp:~/hampug-merged-website/hampug.github.io$ git init .

hint: Using 'master' as the name for the initial branch. This default branch name
hint: is subject to change. To configure the initial branch name to use in all
hint: of your new repositories, which will suppress this warning, call:
hint: 
hint: 	git config --global init.defaultBranch <name>
hint: 
hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
hint: 'development'. The just-created branch can be renamed via this command:
hint: 
hint: 	git branch -m <name>

Initialised empty Git repository in /home/ian/hampug-merged-website/hampug.github.io/.git/
ian@hp:~/hampug-merged-website/hampug.github.io$ # git config --global init.defaultBranch <name>
ian@hp:~/hampug-merged-website/hampug.github.io$ git config --global init.defaultBranch mainian@hp:~/hampug-merged-website/hampug.github.io$ git config --global branch -m main
error: key does not contain a section: branch
ian@hp:~/hampug-merged-website/hampug.github.io$ git branch -m main
ian@hp:~/hampug-merged-website/hampug.github.io$ git remote add origin git@github.com:irsbugs/hampug.github.io.git
ian@hp:~/hampug-merged-website/hampug.github.io$ #  nikola github_deploy
ian@hp:~/hampug-merged-website/hampug.github.io$ source nikola-env/bin/activate
bash: nikola-env/bin/activate: No such file or directory
ian@hp:~/hampug-merged-website/hampug.github.io$ cd ..
ian@hp:~/hampug-merged-website$ cd ..
ian@hp:~$ source nikola-env/bin/activate
(nikola-env) ian@hp:~$ cd hampug-merged-website/
(nikola-env) ian@hp:~/hampug-merged-website$ cd hampug.github.io/


(nikola-env) ian@hp:~/hampug-merged-website/hampug.github.io$ nikola github_deploy
Scanning posts.....done!
Scanning posts.....done!
[2025-03-06 12:30:33] INFO: github_deploy: ==> ['git', 'checkout', 'src']
error: pathspec 'src' did not match any file(s) known to git
[2025-03-06 12:30:33] INFO: github_deploy: ==> ['git', 'checkout', '-b', 'src']
Switched to a new branch 'src'
[2025-03-06 12:30:33] INFO: github_deploy: ==> ['git', 'add', '.']
[2025-03-06 12:30:33] INFO: github_deploy: ==> ['git', 'diff-index', '--quiet', 'HEAD']
fatal: ambiguous argument 'HEAD': unknown revision or path not in the working tree.
Use '--' to separate paths from revisions, like this:
'git <command> [<revision>...] -- [<file>...]'
[2025-03-06 12:30:33] INFO: github_deploy: ==> ['git', 'commit', '-am', 'Nikola auto commit.\n\nNikola version: 8.3.1']
[src (root-commit) f07c56d] Nikola auto commit.
 84 files changed, 5442 insertions(+)
 create mode 100644 .gitignore
 create mode 100644 conf.py
 create mode 100644 files/assets/css/custom.css
 create mode 100644 images/HamPUG_hidetitle_about.png
 create mode 100644 images/HamPUG_hidetitle_index.png
 create mode 100644 images/HamPUG_initial_about_page.png
 ...snip...
 create mode 100644 pages/steps.rst
 create mode 100644 pages/website-creation.meta
 create mode 100644 pages/website-creation.rst
[2025-03-06 12:30:33] INFO: github_deploy: ==> ['ghp-import', '-n', '-m', 'Nikola auto commit.\n\nSource commit: f07c56dacdeadac6a57542c60d478605fd7072d2\nNikola version: 8.3.1', '-p', '-r', 'origin', '-b', 'main', 'output']
git@github.com: Permission denied (publickey).
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
Traceback (most recent call last):
  File "/home/ian/nikola-env/bin/ghp-import", line 8, in <module>
    sys.exit(main())
             ^^^^^^
  File "/home/ian/nikola-env/lib/python3.12/site-packages/ghp_import.py", line 300, in main
    ghp_import(args.pop("directory"), **args)
  File "/home/ian/nikola-env/lib/python3.12/site-packages/ghp_import.py", line 285, in ghp_import
    git.check_call('push', opts['remote'], opts['branch'])
  File "/home/ian/nikola-env/lib/python3.12/site-packages/ghp_import.py", line 119, in check_call
    sp.check_call(['git'] + list(args), **kwargs)
  File "/usr/lib/python3.12/subprocess.py", line 413, in check_call
    raise CalledProcessError(retcode, cmd)
subprocess.CalledProcessError: Command '['git', 'push', 'origin', 'main']' returned non-zero exit status 128.
[2025-03-06 12:30:35] ERROR: github_deploy: Failed GitHub deployment -- command ['ghp-import', '-n', '-m', 'Nikola auto commit.\n\nSource commit: f07c56dacdeadac6a57542c60d478605fd7072d2\nNikola version: 8.3.1', '-p', '-r', 'origin', '-b', 'main', 'output'] returned 1


Settting up[ a SSH key

Follow these direction:

https://medium.com/featurepreneur/setting-up-ssh-key-with-github-for-ubuntu-cd8f2fabf25b

ian@hp:~$ ssh-keygen -t rsa -b 4096 -C "irsbugs@hotmail.com"

Generating public/private rsa key pair.
Enter file in which to save the key (/home/ian/.ssh/id_rsa): 
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /home/ian/.ssh/id_rsa
Your public key has been saved in /home/ian/.ssh/id_rsa.pub

The key fingerprint is:

SHA256:2yLln2xhoef7PBJV8pa16t1Jm6A8eR3NLpLbo6mcrWY irsbugs@hotmail.com

The key's randomart image is:
+---[RSA 4096]----+
|                 |
|            . . .|
|             + o.|
|          . . +. |
|        S. o ....|
|       o.o=  o oo|
|      . ++oo+.=.*|
|       . =EX+=o*o|
|         +X*X=.o |
+----[SHA256]-----+

ian@hp:~$ ls .ssh -l
total 20
-rw------- 1 ian ian 3389 Mar  6 13:21 id_rsa
-rw-r--r-- 1 ian ian  745 Mar  6 13:21 id_rsa.pub
-rw------- 1 ian ian 4764 Feb 19 17:54 known_hosts
-rw------- 1 ian ian 3502 Jun 29  2023 known_hosts.old


ian@hp:~$ cd .ssh
ian@hp:~/.ssh$ ls
id_rsa  id_rsa.pub  known_hosts  known_hosts.old
ian@hp:~/.ssh$ cat id_rsa
-----BEGIN OPENSSH PRIVATE KEY-----
b3BlbnNzaC1rZXktdjEAAAAABG5vbmUAAAAEbm9uZQAAAAAAAAABAAACFwAAAAdzc2gtcn
NhAAAAAwEAAQAAAgEAwLYukSy2JNMA44PShD0dHTRND0FVKKcHab8WSDTaRCeIRCT4gbYG
/hh5Qgj015GD/7JfOpY+QtHoKuKqxZlHWO/S7Dv0kE0qbPcMfN90q5l0OJPltpNqiysCuU
u5fcEHG6rOj1fwuxJUFLuGr/rjLpNqhotyDk+9+YTM2yzYr+SjU7ACSFP3h6nps6woilC5
pvR1PXGZ21AvPii3AUDTZ8rs7PzNUs8XvzdsCGHdj+GwAxy8pn1CoxNErzMycrq80hi5D/

2kLeqsla/ixYRYPzwaA8gcHREVv7kKU/A6KV8v+qFT5wbUJqJVczXewIIYPyBbCUP2em6v
OrNf15mmCK4IWDAUw5gmfexHdlJSAvB32/LXHzXIkIOPU126xwtl621lYNahP0koMLqe2+
0MMNvnM3ecNXwuqrcWP54n8koIchH1k4oU0gnqnabpwNyrtAkKYUj3oxCJB72gcYwwKpaz
fNbSAO4ngFZzAAAAE2lyc2J1Z3NAaG90bWFpbC5jb20BAgMEBQYH
-----END OPENSSH PRIVATE KEY-----
ian@hp:~/.ssh$ 
ian@hp:~/.ssh$ 
ian@hp:~/.ssh$ ls
id_rsa  id_rsa.pub  known_hosts  known_hosts.old
ian@hp:~/.ssh$ cat id_rsa.pub

ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAACAQDAti6RLLYk0wDjg9KEPR0dNE0PQVUopwdpvxZINNpEJ4hEJPiBtgb+GHlCCPTXkYP/sl86lj5C0egq4qrFmUdY79LsO/SQTSps9wx833SrmXQ4k+W2k2qLKwK5S7l9wQcbqs6PV/C7ElQUu4av+uMuk2qGi3IOT735hMzbLNiv5KNTsAJIU/eHqemzrCiKULmm9HU9cZnbUC8+KLcBQNNnyuzs/M1Szxe/N2wIYd2P4bADHLymfUKjE0SvMzJyurzSGLkP9aekz6nmLHQlYYL4KFnJx/ytup7ZyMbS

ZwEo0DAwm+GnyJ5YNHhxqPhnSHf4wKWSGQxPaTT73PxCcJdVkwalXLHHUpCBZXCMzf9ZjfTl5kkzFY+J9amtDhyTgrBs4GieK94Ic+GWX/VP/XNCZOt3WOlaMO74xEGhTbPOPqymKnIQkJQoYm76t9EuipU5Bqc9eGOn8nHOrfOS3dixoTO5jgsNleMYbVs9uHTutG4YdszJf8aLQQ80Ee9LFTONyhWvpJZI2npRdQXrR+my2sOZ4ZYCxMUaHIaL6Q== irsbugs@hotmail.com


ian@hp:~/.ssh$ eval "$(ssh-agent -s)"
Agent pid 46461
ian@hp:~/.ssh$ 


ian@hp:~/.ssh$ ssh-add ~/.ssh/id_rsa
Identity added: /home/ian/.ssh/id_rsa (irsbugs@hotmail.com)
ian@hp:~/.ssh$ 


After....
Then copy the content (starting from ssh-rsa). Now open your GitHub account and do the following steps :

    Click on your profile in the top right corner and select Settings from the drop-down box.

    Now from the Account Settings section present on the left, select SSH and GPG keys

    To add a new key, Click on New SSH key

    Under the title section, add a name to your key. Then in the key section, paste the key that we copied from our terminal. Finally, click on Add SSH key

You have successfully added a new SSH key to your GitHub account. Hope you found it useful.

===


(nikola-env) ian@hp:~/hampug-merged-website/hampug.github.io$ 
(nikola-env) ian@hp:~/hampug-merged-website/hampug.github.io$ 
(nikola-env) ian@hp:~/hampug-merged-website/hampug.github.io$ nikola github_deploy
Scanning posts.....done!
Scanning posts.....done!
[2025-03-06 13:30:21] INFO: github_deploy: ==> ['git', 'checkout', 'src']
Already on 'src'
[2025-03-06 13:30:21] INFO: github_deploy: ==> ['git', 'add', '.']
[2025-03-06 13:30:21] INFO: github_deploy: ==> ['git', 'diff-index', '--quiet', 'HEAD']
[2025-03-06 13:30:21] INFO: github_deploy: Nothing to commit to source branch.
[2025-03-06 13:30:21] INFO: github_deploy: ==> ['ghp-import', '-n', '-m', 'Nikola auto commit.\n\nSource commit: f07c56dacdeadac6a57542c60d478605fd7072d2\nNikola version: 8.3.1', '-p', '-r', 'origin', '-b', 'main', 'output']
Enumerating objects: 163, done.
Counting objects: 100% (163/163), done.
Delta compression using up to 4 threads
Compressing objects: 100% (101/101), done.
Writing objects: 100% (163/163), 3.83 MiB | 1.45 MiB/s, done.
Total 163 (delta 36), reused 159 (delta 33), pack-reused 0
remote: Resolving deltas: 100% (36/36), done.
To github.com:irsbugs/hampug.github.io.git
 * [new branch]      main -> main
[2025-03-06 13:30:29] INFO: github_deploy: ==> ['git', 'push', '-u', 'origin', 'src']
Enumerating objects: 95, done.
Counting objects: 100% (95/95), done.
Delta compression using up to 4 threads
Compressing objects: 100% (91/91), done.
Writing objects: 100% (95/95), 3.07 MiB | 1.76 MiB/s, done.
Total 95 (delta 5), reused 1 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (5/5), done.
remote: 
remote: Create a pull request for 'src' on GitHub by visiting:
remote:      https://github.com/irsbugs/hampug.github.io/pull/new/src
remote: 
To github.com:irsbugs/hampug.github.io.git
 * [new branch]      src -> src
branch 'src' set up to track 'origin/src'.
[2025-03-06 13:30:35] INFO: github_deploy: Successful deployment
(nikola-env) ian@hp:~/hampug-merged-website/hampug.github.io$ 


===

(nikola-env) ian@hp:~/hampug-merged-website/hampug.github.io$ ls .github
workflows
(nikola-env) ian@hp:~/hampug-merged-website/hampug.github.io$ git status
On branch src
Your branch is up-to-date with 'origin/src'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	.github/

nothing added to commit but untracked files present (use "git add" to track)
(nikola-env) ian@hp:~/hampug-merged-website/hampug.github.io$ git add --all
(nikola-env) ian@hp:~/hampug-merged-website/hampug.github.io$ git status
On branch src
Your branch is up-to-date with 'origin/src'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	new file:   .github/workflows/main.yml

(nikola-env) ian@hp:~/hampug-merged-website/hampug.github.io$ git commit -m "Added .github/workflows/main.yml
> "
[src de380be] Added .github/workflows/main.yml
 1 file changed, 16 insertions(+)
 create mode 100644 .github/workflows/main.yml
(nikola-env) ian@hp:~/hampug-merged-website/hampug.github.io$ 

===


Adding .github/workflow/main.yml


(nikola-env) ian@hp:~/hampug-merged-website/hampug.github.io$ nikola github_deploy
Scanning posts.....done!
Scanning posts.....done!
[2025-03-06 15:20:01] INFO: github_deploy: ==> ['git', 'checkout', 'src']
Already on 'src'
Your branch is ahead of 'origin/src' by 1 commit.
  (use "git push" to publish your local commits)
[2025-03-06 15:20:01] INFO: github_deploy: ==> ['git', 'add', '.']
[2025-03-06 15:20:01] INFO: github_deploy: ==> ['git', 'diff-index', '--quiet', 'HEAD']
[2025-03-06 15:20:01] INFO: github_deploy: Nothing to commit to source branch.
[2025-03-06 15:20:01] INFO: github_deploy: ==> ['ghp-import', '-n', '-m', 'Nikola auto commit.\n\nSource commit: de380bee61535777e2f33f3bacf4b57d87cc9ede\nNikola version: 8.3.1', '-p', '-r', 'origin', '-b', 'main', 'output']
Enumerating objects: 1, done.
Counting objects: 100% (1/1), done.
Writing objects: 100% (1/1), 235 bytes | 235.00 KiB/s, done.
Total 1 (delta 0), reused 0 (delta 0), pack-reused 0
remote: This repository moved. Please use the new location:
remote:   git@github.com:irsbugs/irsbugs.github.io.git
To github.com:irsbugs/hampug.github.io.git
   7091f5c..ca36fd3  main -> main
[2025-03-06 15:20:05] INFO: github_deploy: ==> ['git', 'push', '-u', 'origin', 'src']
Enumerating objects: 6, done.
Counting objects: 100% (6/6), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (5/5), 645 bytes | 645.00 KiB/s, done.
Total 5 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote: This repository moved. Please use the new location:
remote:   git@github.com:irsbugs/irsbugs.github.io.git
To github.com:irsbugs/hampug.github.io.git
   f07c56d..de380be  src -> src
branch 'src' set up to track 'origin/src'.
[2025-03-06 15:20:08] INFO: github_deploy: Successful deployment

(nikola-env) ian@hp:~/hampug-merged-website/hampug.github.io$ 

===

Note above it detected the repository had moved...

remote: This repository moved. Please use the new location:
remote:   git@github.com:irsbugs/irsbugs.github.io.git
To github.com:irsbugs/hampug.github.io.git

===


 remote: Permission to irsbugs/irsbugs.github.io.git denied to github-actions[bot].


 In Settings --> Actions --> General --> Workflow Permissions. Check Read and write permissions
 
 # Needs: Settings --> Actions --> General --> Workflow Permissions. Check Read and write permissions 
 
 ====
 
 (nikola-env) ian@hp:~/hampug-merged-website/hampug.github.io$ git status
On branch src
Your branch is up-to-date with 'origin/src'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   .github/workflows/main.yml
	modified:   pages/history.md

no changes added to commit (use "git add" and/or "git commit -a")

(nikola-env) ian@hp:~/hampug-merged-website/hampug.github.io$ git add --all
(nikola-env) ian@hp:~/hampug-merged-website/hampug.github.io$ git commit -m "Added modified main.yml and modified history.md"
[src c9e25b8] Added modified main.yml and modified history.md
 2 files changed, 3 insertions(+), 1 deletion(-)
(nikola-env) ian@hp:~/hampug-merged-website/hampug.github.io$ git status
On branch src
Your branch is ahead of 'origin/src' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean

=== 
 
 
(nikola-env) ian@hp:~/hampug-merged-website/hampug.github.io$ git status
On branch src
Your branch is ahead of 'origin/src' by 1 commit.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   pages/readme-src/README.md

no changes added to commit (use "git add" and/or "git commit -a")

(nikola-env) ian@hp:~/hampug-merged-website/hampug.github.io$ git add --all

(nikola-env) ian@hp:~/hampug-merged-website/hampug.github.io$ git commit -m "Modified README.md"
[src 584d2ed] Modified README.md
 1 file changed, 124 insertions(+), 62 deletions(-)
 
(nikola-env) ian@hp:~/hampug-merged-website/hampug.github.io$ git status
On branch src
Your branch is ahead of 'origin/src' by 2 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
 
(nikola-env) ian@hp:~/hampug-merged-website/hampug.github.io$ nikola github_deploy

To github.com:irsbugs/hampug.github.io.git
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'github.com:irsbugs/hampug.github.io.git'
hint: Updates were rejected because the remote contains work that you do not
hint: have locally. This is usually caused by another repository pushing to
hint: the same ref. If you want to integrate the remote changes, use
hint: 'git pull' before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.

(nikola-env) ian@hp:~/hampug-merged-website/hampug.github.io$ git config pull.rebase true

(nikola-env) ian@hp:~/hampug-merged-website/hampug.github.io$ git pull
dropping c9e25b8d9c1bd5b12005e420931f81e475042d0f Added modified main.yml and modified history.md 
-- patch contents already upstream 
Successfully rebased and updated refs/heads/src.

(nikola-env) ian@hp:~/hampug-merged-website/hampug.github.io$ nikola github_deploy
Scanning posts.....done!
.  render_posts:timeline_changes
Scanning posts.....done!
[2025-03-06 17:01:17] INFO: github_deploy: ==> ['git', 'checkout', 'src']
Already on 'src'
Your branch is ahead of 'origin/src' by 1 commit.
  (use "git push" to publish your local commits)
[2025-03-06 17:01:17] INFO: github_deploy: ==> ['git', 'add', '.']
[2025-03-06 17:01:17] INFO: github_deploy: ==> ['git', 'diff-index', '--quiet', 'HEAD']
[2025-03-06 17:01:17] INFO: github_deploy: Nothing to commit to source branch.
[2025-03-06 17:01:17] INFO: github_deploy: ==> ['ghp-import', '-n', '-m', 'Nikola auto commit.\n\nSource commit: 85a2b048b17529e4e0fd5b7a0d004220cfee5147\nNikola version: 8.3.1', '-p', '-r', 'origin', '-b', 'main', 'output']
Enumerating objects: 40, done.
Counting objects: 100% (40/40), done.
Delta compression using up to 4 threads
Compressing objects: 100% (13/13), done.
Writing objects: 100% (23/23), 13.79 KiB | 3.45 MiB/s, done.
Total 23 (delta 11), reused 11 (delta 2), pack-reused 0
remote: Resolving deltas: 100% (11/11), completed with 9 local objects.
remote: This repository moved. Please use the new location:
remote:   git@github.com:irsbugs/irsbugs.github.io.git
To github.com:irsbugs/hampug.github.io.git
   16742e1..f52598f  main -> main
[2025-03-06 17:01:20] INFO: github_deploy: ==> ['git', 'push', '-u', 'origin', 'src']
Enumerating objects: 9, done.
Counting objects: 100% (9/9), done.
Delta compression using up to 4 threads
Compressing objects: 100% (5/5), done.
Writing objects: 100% (5/5), 1.48 KiB | 1.48 MiB/s, done.
Total 5 (delta 3), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (3/3), completed with 3 local objects.
remote: This repository moved. Please use the new location:
remote:   git@github.com:irsbugs/irsbugs.github.io.git
To github.com:irsbugs/hampug.github.io.git
   730707e..85a2b04  src -> src
branch 'src' set up to track 'origin/src'.
[2025-03-06 17:01:24] INFO: github_deploy: Successful deployment
(nikola-env) ian@hp:~/hampug-merged-website/hampug.github.io$ git status
On branch src
Your branch is up-to-date with 'origin/src'.

nothing to commit, working tree clean
(nikola-env) ian@hp:~/hampug-merged-website/hampug.github.io$ 


===

 
 

