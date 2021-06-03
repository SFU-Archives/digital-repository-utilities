###### [Digital Repository Utilities](../README.md)

# github-issues-to-pdf Script
This script creating print-friendly pdfs of the full comment string on a GitHub repository's `Issues`.

SFU Archives uses this mainly with its [Software Development Priorities](https://github.com/SFU-Archives/software-development-priorities) repository, where software features for possible development are tracked as GitHub issues. The Archives creates periodic snapshots, typically at the end of a development contract or beginning of planning for a new one. The script outputs the full set of issues, which can then be consolidated in Acrobat as a single pdf file.

The script uses [nodejs](https://nodejs.org/en/), a form of command-line javascript. The script was developed by Alex Garnett and is maintained in its own [GitHub repository](https://github.com/axfelix/github-issues-to-pdf).

**Contents**
- [Installation](#installation)
- [Usage](#usage)
- [Links](#links)

## Installation
Open Terminal to install:
1. Install node: `$ brew install node`.
1. Clone the script library: `$ git clone https://github.com/axfelix/github-issues-to-pdf`.
1. Navigate to the cloned directory: `$ cd github-issues-to-pdf`
1. Install script library's dependencies: `$ npm install`

**Notes:**

- Find the `github-issues-to-pdf` directory in your user home folder; the directory can be moved to any location on your computer.

- To run the script, you will also need a GitHub [personal access token (PAT)](https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/creating-a-personal-access-token); the first time you run the script, GIP will ask for it; you will not need to enter it subsequently.

- When installing, you may get security warnings relating to `https-proxy-agent`. This is because the script was forked from a package that has some outdated dependencies; these are not critical because the script will only be run locally as a one-off and not as part of a server stack.

## Usage
Run the script from Terminal:
1. Navigate to script directory: `$ cd github-issues-to-pdf`.
1. Run the script: `$ npm start`.
1. If this is the first time running the script, you will prompted for a [personal access token](https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/creating-a-personal-access-token).
1. You will be prompted to specify a number of variables:
- `type of repository` ("organization")
- `name of account` (e.g. "sfu-archives")
- `name of repository` (e.g. "software-development-priorities")
- whether or not to specify `year issue was opened`

**Notes:**

- The pdfs (one for each issue) are output to a folder in the script directory, `rendered_PDFs`; the folder will be created if it does not already exist.

## Links
The script was developed by Alex Garnett based on a fork from https://github.com/alexandervalencia/github-issues-to-pdf. Source code and documentation for the SFU script are available at: https://github.com/axfelix/github-issues-to-pdf.

###### Last updated: Nov 16, 2020
