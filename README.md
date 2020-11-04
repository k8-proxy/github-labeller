# Label Synchronisation accross all repositores

### Usage (Automatic)
The label maker and synchronisation utilises a CI pipeline (go.yml) that runs every day at 07:00 BST time and looks out for any new repositories and apply the labels. You can use [crontab] to come up with the desired cron job time to run the workflow.

### Usage (Manual)
1. Install go, if you don't have it installed. Click [here] for directions.
2. Clone the repo
```sh
$ GO111MODULE=off go get github.com/k8-proxy/github-labeller
```
3. Edit the file labels.json with the labels you want synchronised. eg
```sh
{
        "name": "QA Task",
        "description": "Quality Assurance needed",
        "color": "c2e0c6"
    },
    {
        "name": "merge conflict",
        "description": "Indicates a merge conflict.",
        "color": "fbca04"
    },
```
4. Implement the changes
```sh
$ GITHUB_TOKEN=mytoken github-labeller ORGANISATION
```
where "mytoken" is your personal github token, "ORGANISATION" is the organisation to which the repos belong.


# Label Synchronisation for a single repository

1. You'll need Node.js 12+ installed to run GitHub Label Sync. You'll also need a GitHub access token ready so that the the tool will have access to your repositories.

```sh
$ npm install -g github-label-sync
```

2. Download labels.yml into the working directory 

```sh
$ github-label-sync --access-token xxxxxx --labels labels.yml myname/myrepo
```

Note: Running this will delete all labels not in the yml file.

### Default Labels
| Label                         | Description                                   |
| ------                        | ------                                        |
|  bug                          |  Something isn't working                      |
|  documentation                |  Improvements or additions to documentation   |
|  duplicate                    |  This issue or pull request already exists    |
|  enhancement                  |  New feature or request                       |
|  good first issue             |  Good for newcomers                           |
|  help wanted                  |  Extra attention is needed                    |
|  invalid                      |  This doesn't seem right                      |
|  question                     |  Further information is requested             |
|   wontfix                     |  This will not be worked on                   |

### Added labels

| Label                         |  Description                                  |
| ------                        | ------                                        |
|  A1 Injection                 |                                               |
|  A2 Broken Authentication     |                                               |
|  A6 Sensitive Data Exposure   |     |
|  A11 DoS                      |     |
|  ci                           |     |
| Changes requested             |   Indicates that some modifications needs to be implemented |
|  Jupyter Notebook             |  Indicates a local Jupyter Notebook    |
| Merge Conflict                |    Indicates a merge conflict |
|  New Feature                  |     |
|  P0                           |     |
|  P1                           |     |
|  P2                           |     |
|  P3                           |     |
|  PR                           |     |
|  QA task                      |     |
|  Quality                      |     |
|  Refactor                     |   |
|  Research                     |   |
|  Ready for review             |   |
|  Risk - Accepted              |   |
|  Risk - Fixed                 |   |
|  Risk - High                  |   |
|  Risk - Low                   |   |
|  Risk - Medium                |   |
|  Risk - To accept             |   |
|  Risk - To fix                |   |
|  Security                     |   |
|  Test Needed                  |   |
|  Use case                      |   |

[here]: <https://golang.org/doc/install>

[crontab]: <https://crontab.guru/>

[Github-labeller]:<https://github.com/displague/github-labeller>

[GitHub Label Sync]:<https://github.com/Financial-Times/github-label-sync>


### Reference

[Github-labeller]

[GitHub Label Sync]
