┌──(kali㉿kali)-[~]
└─$ export GITHUB_USERNAME=Doom666Di                              
export GITHUB_EMAIL=dmitryvasilev5676@outlook.com
export GITHUB_TOKEN=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
alias edit=subl
                                                                                                                  
┌──(kali㉿kali)-[~]
└─$ cd ${GITHUB_USERNAME}/workspace
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace]
└─$ source scripts/activate
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace]
└─$ rm -r ~/.config
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace]
└─$ mkdir ~/.config                          
mkdir: cannot create directory ‘/home/kali/.config’: File exists
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace]
└─$ rm -r ~/.config
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace]
└─$ rm -rl ~/.config
rm: invalid option -- 'l'
Try 'rm --help' for more information.
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace]
└─$ rm -r ~/.config 
rm: cannot remove '/home/kali/.config': No such file or directory
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace]
└─$ mkdir ~/.config 
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace]
└─$ cat > ~/.config/hub <<EOF
github.com:
- user: ${GITHUB_USERNAME}
  oauth_token: ${GITHUB_TOKEN}
  protocol: https
EOF
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace]
└─$ git config --global hub.protocol https
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace]
└─$ mkdir projects/lab02 && cd projects/lab02
mkdir: cannot create directory ‘projects/lab02’: File exists
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace]
└─$ rm -r projects/lab02
rm: remove write-protected regular file 'projects/lab02/.git/objects/4b/825dc642cb6eb9a060e54bf8d69288fbee4904'? y
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace]
└─$ rm -r projects/lab02
rm: cannot remove 'projects/lab02': No such file or directory
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace]
└─$ mkdir projects/lab02 && cd projects/lab02
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab02]
└─$ echo "# REPO_NAME" >> README.md
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab02]
└─$ git init
hint: Using 'master' as the name for the initial branch. This default branch name
hint: is subject to change. To configure the initial branch name to use in all
hint: of your new repositories, which will suppress this warning, call:
hint:
hint:   git config --global init.defaultBranch <name>
hint:
hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
hint: 'development'. The just-created branch can be renamed via this command:
hint:
hint:   git branch -m <name>
Initialized empty Git repository in /home/kali/Doom666Di/workspace/projects/lab02/.git/
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab02]
└─$ git add README.md
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab02]
└─$ git commit -m "first commit"
[master (root-commit) 8e01ac3] first commit
 1 file changed, 1 insertion(+)
 create mode 100644 README.md
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab02]
└─$ git branch -M main
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab02]
└─$ git remote add origin https://Doom666Di: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@github.com/Doom666Di/lab02.git
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab02]
└─$ git push -u origin main
remote: Repository not found.
fatal: repository 'https://github.com/Doom666Di/lab02.git/' not found
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab02]
└─$ git push -u origin main
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 230 bytes | 230.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/Doom666Di/lab02.git
 * [new branch]      main -> main
branch 'main' set up to track 'origin/main'.
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab02]
└─$ git config --global user.name ${GITHUB_USERNAME}
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab02]
└─$ git config --global user.email ${GITHUB_EMAIL}
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab02]
└─$ git config -e --global
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab02]
└─$ touch README.md
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab02]
└─$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab02]
└─$ git pull origin master
fatal: couldn't find remote ref master
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab02]
└─$ git add README.md
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab02]
└─$ git commit -m"added README.md"
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab02]
└─$ git push origin master
error: src refspec master does not match any
error: failed to push some refs to 'https://github.com/Doom666Di/lab02.git'
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab02]
└─$ git push -u origin main  
To https://github.com/Doom666Di/lab02.git
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'https://github.com/Doom666Di/lab02.git'
hint: Updates were rejected because the remote contains work that you do not                                      
hint: have locally. This is usually caused by another repository pushing to
hint: the same ref. If you want to integrate the remote changes, use
hint: 'git pull' before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab02]
└─$ git pull origin main  
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (3/3), 957 bytes | 957.00 KiB/s, done.
From https://github.com/Doom666Di/lab02
 * branch            main       -> FETCH_HEAD
   8e01ac3..39c5e47  main       -> origin/main
Updating 8e01ac3..39c5e47
Fast-forward
 .gitignore | 4 ++++
 1 file changed, 4 insertions(+)
 create mode 100644 .gitignore
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab02]
└─$ git log
commit 39c5e47d610b60453bd2c4ba04f58722ff2365cd (HEAD -> main, origin/main)
Author: Doom666Di <dmitryvasilev5676@outlook.com>
Date:   Sun Mar 9 16:50:29 2025 +0300

    Create .gitignore
    
    ignore

commit 8e01ac3d9d9854cdf176e6e7e9e62281e523fb0a
Author: Doom666Di <dmitryvasilev5676@outlook.com>
Date:   Sun Mar 9 09:33:20 2025 -0400

    first commit
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab02]
└─$ mkdir sources
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab02]
└─$ mkdir include 
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab02]
└─$ mkdir examples
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab02]
└─$ cat > sources/print.cpp <<EOF
#include <print.hpp>

void print(const std::string& text, std::ostream& out)
{
  out << text;
}

void print(const std::string& text, std::ofstream& out)
{
  out << text;
}
EOF
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab02]
└─$ cat > include/print.hpp <<EOF
#include <fstream>
#include <iostream>
#include <string>

void print(const std::string& text, std::ofstream& out);
void print(const std::string& text, std::ostream& out = std::cout);
EOF
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab02]
└─$ cat > examples/example1.cpp <<EOF
#include <print.hpp>

int main(int argc, char** argv)
{
  print("hello");
}
EOF
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab02]
└─$ cat > examples/example2.cpp <<EOF
#include <print.hpp>

#include <fstream>

int main(int argc, char** argv)
{
  std::ofstream file("log.txt");
  print(std::string("hello"), file);
}
EOF
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab02]
└─$ edit README.md
Command 'subl' not found, did you mean:
  command 'publ' from deb atfs
  command 'subs' from deb libsubtitles-perl
Try: sudo apt install <deb name>
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab02]
└─$ nano README.md
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab02]
└─$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        examples/
        include/
        sources/

no changes added to commit (use "git add" and/or "git commit -a")
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab02]
└─$ git add .
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab02]
└─$ git commit -m"added sources"
[main a385b8c] added sources
 5 files changed, 33 insertions(+)
 create mode 100644 examples/example1.cpp
 create mode 100644 examples/example2.cpp
 create mode 100644 include/print.hpp
 create mode 100644 sources/print.cpp
                                                                                                                  
┌──(kali㉿kali)-[~/Doom666Di/workspace/projects/lab02]
└─$ git push origin main  
Enumerating objects: 12, done.
Counting objects: 100% (12/12), done.
Delta compression using up to 4 threads
Compressing objects: 100% (7/7), done.
Writing objects: 100% (10/10), 965 bytes | 965.00 KiB/s, done.
Total 10 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/Doom666Di/lab02.git
   39c5e47..a385b8c  main -> main
