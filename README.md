# Auto-complete

In online github editor make sure that cursor is set in the right place - only then auto complete appears.   

No auto-complete:
![001-online-edit-not-working-auto-complete](./images/001-online-edit-not-working-auto-complete.png)  
Auto-complete:
![002-online-edit-working-auto-complete](./images/002-online-edit-working-auto-complete.png)
VSCode auto-complete seems to be fine:
![003-vscode-edit-working-auto-complete.png](./images/003-vscode-edit-working-auto-complete.png)


# Run multiple commands.

This will run only one command npm install and second command npm test will be **silently skipped**:
```
run:
    npm install
    npm test
```
Use ```|``` to run multiple commands:
```
run: |
    npm install
    npm test
```

# Jobs

## Sharing data between jobs
Each job executes on fresh instance of a virtual environment that`s why jobs do not share anything (like file system). To share artifacts in the same workflow between different jobs use actions upload and download to share to build output which is needed to run the unit tests.
https://docs.github.com/en/actions/guides/storing-workflow-data-as-artifacts

## By default jobs run in parallel

Use ```needs: [job-name]``` to control when to start particular jobs.

# Tools

## Visualization

Use https://github-actions-hero.vercel.app/ and its playground to visualize a workflow.
In this view it is easy to understand which parts are executed in parallel.
https://github-actions-hero.vercel.app/playground   

# Team approval workflow

[approval-workflow.yml](./.github/workflows/approval-workflow.yml])

* easy way to see when enough approvals has been achieved
* branch protections: https://github.com/kicaj29/github-actions-demo/settings/branches
* required review approvals
* matrix build
* save build artifacts
* dedicated test job

# Giphy generator

[giphy-generator.yml](./.github/workflows/giphy-generator.yml)

Using https://developers.giphy.com/dashboard/?create=true create a GIPHY_TOKEN and add it to the secrets: 
![004-giphy-token.png](./images/004-giphy-token.png)

If we will add comment that starts with `/giphy` then selected git will be added by this workflow:

![005-giphy-gif.png](./images/005-giphy-gif.png)

# links
https://github.com/a-a-ron/github-actions-course-template   
http://github.com/marketplace   
https://github.com/marketplace/actions/label-approved-pull-requests   
https://github.com/marketplace/actions/giphy-generator   
https://lab.github.com   
test
