
Documentation:https://docs.github.com/en/actions/reference/workflows-and-actions/events-that-trigger-workflows#push


GitHub Actions is a CI/CD platform/tool built into GitHub. It can be used for:
• CI (Continuous Integration): Automatically build, test, and validate code when developers push changes or create pull requests. ￼￼
• CD (Continuous Delivery/Deployment): Automatically package and deploy applications to environments such as Azure, AWS, Kubernetes, or on-premises servers after tests pass. ￼￼
GitHub Actions uses workflows (defined in YAML files under .github/workflows/) to automate these tasks. Workflows can be triggered by events like:
• Code pushes
• Pull requests
• Scheduled runs
• Manual triggers ￼￼
<img width="1890" height="998" alt="image" src="https://github.com/user-attachments/assets/c019d1f3-abac-4d01-87a2-786bf8dbe088" />






<img width="2004" height="1058" alt="image" src="https://github.com/user-attachments/assets/012ecf01-c736-4fab-b20f-a1649aff8811" />





i have created my first repo locally and also in github page
mkdir firstrepo
echo "# firstrepo" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/mvenkatadry-debug/firstrepo.git
git push -u origin main



###
git checkout is only temporary move. these commit moves cannot be reflected in main branch
Exactly. ✅ You're getting the core Git concept now.
When you run:
git checkout cc6bdd9

Git moves only HEAD to that commit.
Before:
HEAD -> main -> 6c29fad

After:
HEAD -> cc6bdd9
main -> 6c29fad

Notice that main did not move.
That's why Git said:
HEAD detached at cc6bdd9

You're just viewing an old snapshot of the repository.
###





<img width="1596" height="882" alt="image" src="https://github.com/user-attachments/assets/7ab2e0bd-ba00-48c6-b538-bceefd6f8504" />


git revert is the safe way to undo a commit.
Unlike git checkout (temporary view) or git reset (moves a branch), git revert creates a new commit that reverses the changes of an earlier commit. It does not rewrite history. 



vm@VCHOWDARY-MAC firstrepo % git log                                            
commit dd92836e6b4cf95499e2d4069e350f2a81c749e1 (HEAD -> main, origin/main)
Author: venkatadry <mullapudi67@gmail.com>
Date:   Tue Jul 28 14:51:59 2026 -0600

    Revert "added message"
    
    This reverts commit 6c29fad354bd775ce52d5883b808f9057d42e99c.

commit 6c29fad354bd775ce52d5883b808f9057d42e99c
Author: venkatadry <mullapudi67@gmail.com>
Date:   Tue Jul 28 14:01:57 2026 -0600


git revert 6c29fad354bd775ce52d5883b808f9057d42e99c ##so i moved to this commit where the file is only empty.so what ever commit u have to go  u have to give this




<img width="1802" height="1096" alt="image" src="https://github.com/user-attachments/assets/0936cde5-ea28-4543-853d-3d407403b4f1" />
