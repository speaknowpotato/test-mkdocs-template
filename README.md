# mkdocs-template

Mkdocs Template using github pages and actions

## How to build mkdocs template

1. init repo
2. create `mkdocs.yml`
3. set up github pages
![github pages](github_pages.png)

Source: Deploy from a branch

Branch: gh-pages/root

4. set up github actions
![github action](github_action.png)
```yaml
name: ci 
on:
  push:
    branches:
      - main
jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: actions/setup-python@v2
        with:
          python-version: 3.x
      - run: pip install mkdocs-material
      - run: pip install mkdocs-awesome-pages-plugin
      - run: pip install mkdocs-jupyter
      - run: pip install mkdocs-git-revision-date-localized-plugin
      - run: mkdocs gh-deploy --force
```
5. view the [https://speaknowpotato.github.io/mkdocs-template/](https://speaknowpotato.github.io/mkdocs-template/)

