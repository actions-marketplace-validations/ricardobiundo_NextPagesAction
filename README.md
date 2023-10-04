# Build Next.js and deploy it to Github Pages 🚀
This Action will Build your Next.js Project and deploy it to Github Pages

## Getting Started 🎉

1. Prepare your package.json file by adding:
```json
{
  "scripts": {
    "build": "next build",
    "export": "next export",
  }
}
```

2. Create a Github Actions Workflow file in your own reposiroty and add this to it (and replace "YourGithubName" and "YourRepoName" with your user names)

```yml
name: Build Next.js
on: [push]
jobs:
  build_next:
    runs-on: ubuntu-latest
    name: Build Next.js
    steps:
    - uses: actions/checkout@v3
    - id: Build-Next
      uses: ricardobiundo/NextPagesAction@1.0.2
      with:
        username: 'YourGithubName'
        reponame: 'YourRepoName'
        token: ${{ secrets.GITHUB_TOKEN }} # Leave this line unchanged
```
3. Go to Settings -> Scroll down to GitHub Pages -> Select `gh-pages` as branch and `/` as directory 

## Options 🔧
|   Name   |            Description           |     Default    | Required |
|:--------:|:--------------------------------:|:--------------:|:--------:|
| username |           Your username          |        -       |     ✅    |
| reponame |       Your repository name       |        -       |     ✅    |
|   token  | Please leave this line unchanged |        -       |     ✅    |
| gitemail |         Git commit email         | CI@example.com |     ❌    |
|  gitname |          Git commit name         |       CI       |     ❌    |
|  gitmsg  |        Git commit message        |     deploy     |     ❌    |
|   cname  |           Custom domain          |        -       |     ❌    |
|  useyarn |         Use yarn to build        |      false     |     ❌    |
