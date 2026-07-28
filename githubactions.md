
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
