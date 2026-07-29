
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




<img width="1944" height="1098" alt="image" src="https://github.com/user-attachments/assets/337ffdf4-ae89-42eb-9bbd-1c7dcdb12c46" />

repository_Disaptch :https://www.anantacloud.com/post/github-repository-dispatch-event-for-custom-triggers




<img width="1900" height="1144" alt="image" src="https://github.com/user-attachments/assets/7dac888b-7fbb-4b3c-a52e-b36b60271977" />

In fact, you need Node.js and npm already installed before you can run
npm install"
I meant for any Node.js/JavaScript project that uses npm. 



uses keyword when u want to use action






###
What happens when you run npm ci?
Suppose your project contains:
// package.json
{
  "dependencies": {
    "express": "^4.21.0"
  }
}
// package-lock.json
{
  "dependencies": {
    "express": {
      "version": "4.21.2"
    }
  }
}
When you run:
npm ci
npm:
	1	Deletes the existing node_modules folder (if present). 12
	2	Reads package-lock.json. 13
	3	Installs the exact versions from the lock file. 13
	4	Does not modify package.json or package-lock.json. 12
Why use it in GitHub Actions?
Typical workflow:
steps:
  - uses: actions/checkout@v4

  - uses: actions/setup-node@v4
    with:
      node-version: 20

  - run: npm ci

  - run: npm test
This ensures every build uses the same dependency versions, making builds reproducible and reliable. 13
npm ci vs npm install
npm ci
npm install
Requires package-lock.json
Can work without lock file
Installs exact locked versions
May update lock file
Removes node_modules first
Reuses existing modules
Fails if lock file and package.json differ
May update lock file to resolve differences
Best for CI/CD
Best for local development
13
Why do pipelines use npm ci?
Because if Developer A has:
lodash 4.17.21
and Developer B accidentally gets a different compatible version, builds can behave differently. npm ci forces everyone—including build agents—to use the exact versions recorded in package-lock.json. 13
Rule of thumb:
	•	During development: npm install
###

The flow is:
1. actions/checkout → downloads the source code.
2. npm ci → installs all required packages.
3. npm test → runs the tests using those installed packages.
Files you'll commonly see



<img width="1622" height="558" alt="image" src="https://github.com/user-attachments/assets/88655390-0607-4dd3-b3f8-47255815eb1b" />

###
