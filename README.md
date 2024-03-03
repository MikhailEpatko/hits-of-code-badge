# hits-of-code-badge 
![Hits-of-Code Badge](https://github.com/MikhailEpatko/hits-of-code-badge/blob/image-data/hits.svg)


GitHub action with hoc.
**hoc** - is a command line tool to calculate Hits-of-Code metric in a source code repository (at the moment it supports Git 2+ and Subversion 1.7+). 
 You can read more about Hits-of-Code metric in this blog post: Hits-of-Code Instead of SLoC.

[**hoc** project page](https://github.com/yegor256/hoc/tree/master)

To install action copy the workflow code into a .github/workflows/main.yml file in your repository

```
on: [push]

jobs:
  lines_counter_job:
    runs-on: ubuntu-latest
    name: A job to count hits of code
    steps:
      - uses: actions/checkout@v4
      - id: badge-generator
        uses: ./                  # write the action name instead
        with:
          dir: '.'                # default value - include all files
          since: '2000-01-01'     # default value - '2000-01-01'
          before: '2024-03-03'    # default value - now day
```

The badge will be generated in **image-data** branch of your repository. For this you need to configure [Setting the permissions of the GITHUB_TOKEN for your repository](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/enabling-features-for-your-repository/managing-github-actions-settings-for-a-repository#setting-the-permissions-of-the-github_token-for-your-repository).