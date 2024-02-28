# r-releases

[![status](https://www.repostatus.org/badges/latest/concept.svg)](https://www.repostatus.org/#concept)

`r-releases` is a community-curated [R universe](https://github.com/r-universe-org/help) of R packages which are distributed as tags and releases on GitHub. The GitHub repository at <https://github.com/r-releases/r-releases> allows anyone to contribute their package releases to this universe.

Please note that `r-releases` is currently a concept, barely even a prototype. We hope to eventually use it for production purposes, but it is far from ready at the moment.

# How to install a package from `r-releases`

To install a package from `r-releases` (for example, `jsonlite`), open R and run:

```r
install.packages("jsonlite", repos = "https://r-releases.r-universe.dev")
```

# How to add your package

To add your package to `r-releases`, first put your package in a GitHub or GitLab repository. Then, open a [GitHub pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests) to <https://github.com/r-releases/r-releases.r-universe.dev> to add one or more text files to the [`packages` folder](https://github.com/r-releases/r-releases/tree/main/packages) of <https://github.com/r-releases/r-releases>. The name of each file should be the package name, and the only contents of the file should be the URL of the package. See the [`packages` folder](https://github.com/r-releases/r-releases/tree/main/packages) folder for examples.

# How to edit or remove packages

To edit or remove one or more packages, submit a pull request to edit the files in the  [`packages` folder](https://github.com/r-releases/r-releases/tree/main/packages). Your pull request will need to be briefly reviewed by an `r-releases` administrator (see below).

# What do I do if my pull request is flagged for manual review?

Sometimes, automated reviews of pull requests may fail, or you may deliberately be trying the change a URL or remove a package. In all those cases, manual review is required if you intend to pursue the pull request as is. If your pull request is flagged for manual review, then an `r-releases` administrator will review the pull request and let you know about next steps. All we are looking for is that the package and the URL are complete and correct and that the URL attributes proper ownership. It is the responsibility of the package maintainer to implement tests that ensure it is working properly and working well with the other packages that depend on it (see test results at <https://r-releases.r-universe.dev>.

If the manual review was triggered by an error you know how to fix, please close the current pull request and submit a different one. Automated checks ignore pull requests flagged for manual review, but they do process new pull requests from the beginning.

# What happens next

Every hour, a GitHub Actions workflow from <https://github.com/r-releases/r-releases.r-universe.dev> combs through the pull requests at <https://github.com/r-releases/r-releases/pulls> and automatically merges the ones that add new packages with correct-looking URLs. Pull requests that cannot be automatically merged are either closed or flagged for manual review. 

Also every hour, another GitHub Actions workflow in <https://github.com/r-releases/r-releases.r-universe.dev> collects all the packages and URLs from the [`packages` folder](https://github.com/r-releases/r-releases/tree/main/packages) folder and builds the `packages.json` file for the R universe at <https://github.com/r-releases/r-releases.r-universe.dev>. It uses the `"branch": "*release"` field in the JSON file so that each new GitHub tag and release sends the build to the universe. Development versions are not tracked.

Once your package is in `packages.json`, each new GitHub tag and release you create will publish your package to <https://r-releases.r-universe.dev> so others can install it. Please visit <https://github.com/r-releases/r-releases.r-universe.dev> and <https://r-releases.r-universe.dev> for progress and status updates on your package.
