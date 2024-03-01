To contribute your packages to the r-releases R universe, please create a text file for each new package and store all the text files in the `packages/` folder. Each text file has these requirements:

1. The name of the file is the package name.
2. The file contains a single line with the package URL. The URL must be authentic and genuine. It must be the true location of the package according to its true owners. Almost always, this the URL of a repository from GitHub or GitLab, such as https://github.com/r-lib/gh.
3. The file ends with a newline character. (A terminating newline is included automatically if you create the file using the GitHub web interface.)

In rare cases, your package may be in a subdirectory of a GitHub repo, in which case you may write custom JSON with fields `package`, `url`, `subdir`, and `branch`, and the `branch` field must be `"*release"`. Example:

```json
{
  "package": "paws.analytics",
  "url": "https://github.com/paws-r/paws",
  "subdir": "cran/paws.analytics",
  "branch": "*release"
}
```

Please visit https://github.com/r-releases/help for more information. Please send bug reports to https://github.com/r-releases/help/issues and other feedback and questions to https://github.com/r-releases/help/discussions.
