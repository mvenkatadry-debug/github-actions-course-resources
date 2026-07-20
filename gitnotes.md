git installation

vm@VCHOWDARY-MAC githubactions %  git --version
git version 2.39.5 (Apple Git-154)
vm@VCHOWDARY-MAC githubactions % 

After installing Git, you can also configure it

git config --global user.name "your-username"
git config --global user.email "your-email”

git config --global user.name "venkatadry"
git config --global user.email "mullapudi67@gmail.com”
TO create a git repository
mkdir git-demo
cd git-demo
VCHOWDARY-MAC:git-demo vm$ git init
Initialized empty Git repository in /Users/vm/git-demo/.git/
VCHOWDARY-MAC:git-demo vm$ 
The .git folder created has all metaqdata
When a file is created using can see in vscode U
touch index.html
if u want to add the files in subfolder fuldername/flename
vm@VCHOWDARY-MAC git-demo % git add index.html
Now it is ataged so it shows A
vm@VCHOWDARY-MAC git-demo % git status On branch main No commits yet Changes to be committed: (use "git rm --cached <file>..." to unstage) new file: index.html vm@VCHOWDARY-MAC git-demo %

To commit git commit -m "my commit"
vm@VCHOWDARY-MAC git-demo % git commit -m "first commit"
[main (root-commit) 222da0e] first commit
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 index.html
vm@VCHOWDARY-MAC git-demo % 



mover between commits
git checkout  id
tempoarily move to other commit
ex v1,v2,v3
we can move to commit v2 to see the changes only in v2 ignoring v3

to check the previous commits
#git log



 
